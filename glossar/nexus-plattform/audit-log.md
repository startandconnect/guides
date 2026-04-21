---
title: Audit Log
order: 15
excerpt: Wer hat wann was geaendert
---

# Audit Log

Protokoll aller Datenaenderungen in Nexus. Wer hat wann was an welcher Entity geaendert, welche Felder genau.

## Warum wichtig

- **Nachvollziehbarkeit** - "hat Kathi den Preis geaendert oder war das ein Bug?"
- **DSGVO** - Artikel 5 verlangt Rechenschaftspflicht
- **GoBD** - Buchhaltungs-Aenderungen nachvollziehbar
- **Security** - bei Compromise-Verdacht Log checken
- **Debugging** - "der Kunde sagt er hat nie zugestimmt, was sagt das Log?"

## Was wird geloggt

Seit 2026-04-20 sind 11 Resources mit Audit-Log integriert:
- Order, Product, Invoice, Subscription
- Customer, Contact, Deal
- Page, Blog-Post
- Event, Form
- Coupon, Payment, ApiKey, User, EmailTemplate, MediaFile, ContactList, NewsletterSegment, NewsletterBroadcast, ProductCategory

Plus einige weitere via Auto-Whitelist der Prisma-Extension.

## Was im Log steht

Pro Eintrag:
- **Zeitstempel** - wann
- **User** - wer (oder SYSTEM bei automatisierten Aenderungen)
- **Aktion** - CREATE / UPDATE / DELETE
- **Entity** - welche Resource + ID
- **Changed Fields** - welche Felder mit Vorher/Nachher
- **Source** - MIDDLEWARE (automatisch) oder MANUAL (explizit gelogged)

## Wo einsehen

- **Pro Detail-Seite** - Tab "Aenderungshistorie" (z.B. `/manage/orders/[id]/audit-log`)
- **Zentral** - `/manage/logs/audit` (wenn aktiviert)

## Retention

Standard: 10 Jahre (konfigurierbar via `audit.retentionYears` Setting). Nach Ablauf werden Eintraege durch Cron-Job geloescht. Wichtig fuer GoBD-Konformitaet.

## Security-Log separat

Auth-relevante Events (Login, Logout, Password-Change, API-Key-Create) landen im separaten SecurityLog. Unterschiedliche Retention, unterschiedliche Ansicht.

## Activity-Log separat

Kunden-seitige Events (Bestellung, Newsletter-Anmeldung, Support-Kontakt) landen im Activity-Log. Zeigt sich in der Kunden-Detail-Timeline.

## Not audited

- Reine Reads (niemand schaut auf eine Order)
- System-interne Counter-Updates (usageCount etc.)
- Tracking-Events im Marketing-Analytics
