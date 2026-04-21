---
title: Delivery Action
order: 11
excerpt: Was nach einem Kauf passieren soll
---

# Delivery Action

Eine Aktion, die nach einem Event (Kauf, Refund, Event-Buchung, Abo-Start) ausgefuehrt wird. Nexus-Version einer "Marketing-Automation" oder "Post-Purchase-Workflow".

## Typische Delivery-Actions

- **Willkommens-E-Mail senden** mit Kurs-Links
- **Zugang freischalten** (Kurs, Community, Premium-Content)
- **WAIT X Tage** bevor naechste Aktion
- **Slack / Discord-Nachricht** an Admin
- **Webhook an eigenes System**
- **Provisioning** einer neuen Instance (Server-Management-Plugin)
- **Custom HTTP-Call** an externes Tool

## Trigger

Jeder Delivery-Action hat einen [Trigger](/glossar/nexus-plattform/trigger):

- `PURCHASE` - Order bezahlt
- `BEFORE_EVENT` - vor einem Event-Termin (z.B. 24h vorher)
- `AFTER_EVENT` - nach Event
- `SUBSCRIPTION_CREATED` - Abo gestartet
- `SUBSCRIPTION_ENDED` - Abo beendet
- `REFUND` - Rueckerstattung
- `TRIAL_ENDED` - Trial abgelaufen

## Konfiguration

Pro Produkt kannst du eine Kette von Delivery-Actions definieren:

```
Order bezahlt → WAIT 1 Min → Send Email "Willkommen" → WAIT 7 Tage → Send Email "Erste Erfahrungen?" → WAIT 14 Tage → Send Email "Bonus-Angebot"
```

Admin-UI unter `/manage/products/[id]/delivery-actions`.

## Execution

- Delivery-Action wird bei Trigger sofort eingeplant (DB-Eintrag `DeliveryActionExecution`)
- Cron-Scheduler laeuft minuetlich, nimmt due Executions
- Bei Fehler: Retry mit exponential backoff
- Status sichtbar pro Order im Admin

## Idempotenz

Jeder Handler ist [idempotent](/glossar/technik-und-api/idempotenz). Cron-Retry fuehrt nicht zu doppelten Emails.

## Cancellation

Bei Refund oder Storno: alle noch PENDING Executions werden als SKIPPED markiert. Also keine Reminder-E-Mails an jemanden der schon storniert hat.

## Custom-Delivery-Action-Types

Plugins koennen eigene Action-Types anbieten:
- `events-plugin` liefert `SEND_EVENT_REMINDER`
- `server-management` liefert `PROVISION_INSTANCE` + `DEPROVISION_INSTANCE`
- `chatbot` liefert `SYNC_KNOWLEDGE_BASE`

## WAIT-Action

Statt fester Dauer kann WAIT auch "bis Event-Datum" oder "bis Subscription abgelaeuft" sein. Ermoeglicht personalisierte Timings ohne pro-Order-Konfiguration.
