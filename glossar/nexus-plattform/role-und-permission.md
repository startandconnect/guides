---
title: Role und Permission
order: 9
excerpt: Wer darf was in deiner Nexus-Instance
---

# Role und Permission

## Role (Rolle)

Ein Satz von Berechtigungen mit einem Namen. Jeder Nutzer in Nexus hat genau eine Rolle.

## Nexus Kern-Rollen

| Rolle | Zweck |
|---|---|
| **OWNER** | Du selbst, voller Zugriff auf alles |
| **SUPER_ADMIN** | wie ADMIN aber inkl. Team-Verwaltung |
| **ADMIN** | Admin-Zugang ohne Billing und Team |
| **MEMBER** | eingeschraenkter Zugriff je nach Scope |
| **SELLER** | Multi-Seller-Marketplace-Verkaeufer (Affiliate-ID) |
| **SUPPORT** | Kundenbetreuung ohne Verkaufs-Rechte |
| **ACCOUNTANT** | Invoices + Payments lesen, keine Aenderung |
| **CUSTOMER** | Endkunde, nur Customer-Portal-Zugriff |

## Permission

Einzelne konkrete Berechtigung wie `orders.create`, `customers.delete`, `settings.update`. Eine Rolle hat viele Permissions.

## Scope

Zusaetzlich zu Permission: wie weit geht sie? Siehe [Scope](/glossar/nexus-plattform/scope).

- `all` - alle Entities dieser Art
- `team` - nur team-interne
- `own` - nur selbst-erstellte
- `none` - keine

Kombination: "SELLER darf `orders.read` mit Scope `own`" = Seller sieht nur seine Orders (wo er als Verkaeufer eingetragen ist).

## Custom Rollen

Du kannst eigene Rollen anlegen: `POST /api/roles` mit eigenen Permissions und Scopes. Beispiel: "Content-Editor" der nur Blog + Pages editieren darf.

## Wo konfigurieren

Admin-UI unter `/settings/access/roles`. Pro Rolle zeigt die Scope-Matrix:
- Resource (Product, Order, Customer, ...)
- Action (read, create, update, delete)
- Scope-Dropdown

Aenderungen greifen sofort durch In-Memory-Cache-Invalidation.

## Implementation-Detail

Unter der Haube nutzt Nexus eine zweigeteilte Pruefung:
- **Gate-Level** - darf die Action generell? (Permission-Check)
- **Row-Level** - welche Rows sieht der User? (Scope-Filter auf Prisma-Ebene)

Das garantiert dass ein Bug in der UI nie dazu fuehrt, dass ein User mehr sieht als er darf. Details in `wiki/products/nexus/permissions-architecture.md`.

## Permission-Ueberblick in der UI

Pro User unter `/manage/users/[id]/permissions` siehst du welche Permissions wirksam sind. Nuetzlich fuer Debugging.
