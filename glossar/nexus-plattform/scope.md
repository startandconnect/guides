---
title: Scope
order: 10
excerpt: Wie weit eine Permission reicht
---

# Scope

Erweiterung des Permission-Konzepts. Waehrend Permission sagt "darf er oder nicht", sagt Scope "wieviel sieht er davon".

## Vier Scope-Levels

- **`all`** - alle Entities. Beispiel: OWNER sieht alle Orders.
- **`team`** - nur team-weit geteilte. Beispiel: MEMBER sieht alle Orders wo Team-Mitglied zugeordnet ist.
- **`own`** - nur selbst-erstellte oder explizit zugeordnete. Beispiel: SELLER sieht nur Orders wo er Affiliate-Seller ist.
- **`none`** - nichts. Beispiel: CUSTOMER sieht keine Admin-Orders.

## Wie wirkt Scope

Zwei Ebenen:

**Gate-Level** (UI-Sichtbarkeit):
- Wenn Scope `none`: Menu-Eintrag versteckt, API liefert 403
- Wenn Scope `own` oder hoeher: Zugang erlaubt

**Row-Level** (Daten-Filter):
- Per Prisma-Extension wird automatisch ein WHERE-Filter injiziert
- Beispiel: SELLER fetcht `/api/orders` → Extension haengt `WHERE affiliateSellerId = currentUser.id` an

Das passiert transparent fuer den Entwickler. Wenn ein Plugin-Entwickler `prisma.order.findMany()` schreibt, werden Scope-Filter automatisch angewandt.

## Scope-Matrix

Admin-UI unter `/settings/access/roles`:

| Resource | Action | OWNER | ADMIN | SELLER | CUSTOMER |
|---|---|---|---|---|---|
| Order | read | all | all | own | none |
| Order | update | all | all | own | none |
| Order | delete | all | all | none | none |
| Customer | read | all | all | own | none |

Jede Zelle ist ein Dropdown, aendert pro Rolle x Resource x Action.

## Overrides pro Instance

Die Scope-Matrix hat Defaults im Code. Admin kann pro Instance Overrides setzen (z.B. "unser SELLER darf auch Order-Delete"). Overrides sind in DB-Tabelle `RoleScopeOverride` gespeichert.

## Coverage-Warnungen

Nicht jede Resource x Rolle-Kombination hat einen funktionierenden Row-Level-Filter. Die Scope-Matrix zeigt gelbes ⚠ wenn du eine Kombi konfigurierst die nur Gate-Level wirkt (nicht Row-Level). Das verhindert, dass du dich auf Filter verlaesst die nicht da sind.

## Design-Prinzip

**Whitelist statt Blacklist.** Default-Deny: wenn keine Regel matched, ist die Antwort "nein". Sicher gegen Vergesslichkeit.
