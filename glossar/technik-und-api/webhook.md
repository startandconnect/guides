---
title: Webhook
order: 3
excerpt: Wenn der Server anruft statt du fragen musst
---

# Webhook

Event-getriebene Benachrichtigung zwischen Systemen. Statt dass du staendig nachfragst ("Gibt's was neues?"), ruft das Quell-System dich aktiv an wenn etwas passiert.

## Beispiel

Stripe und Nexus:
- Kunde zahlt mit Kreditkarte
- Stripe bucht ab
- Stripe sendet Webhook an Nexus: "Hey, Payment #pi_123 ist erfolgreich"
- Nexus markiert die Order als bezahlt, verschickt Bestaetigungs-Email

Ohne Webhooks muesste Nexus jede Sekunde bei Stripe nachfragen - unsinnig.

## Technisch

Webhook ist einfach ein HTTP POST an eine definierte URL. Body enthaelt JSON mit dem Event.

Empfaenger muss:
1. Den Webhook-Endpunkt beim Absender registrieren
2. POST-Request empfangen und parsen
3. In akzeptabler Zeit (<10 Sekunden typisch) mit 200 antworten

## Signatur-Validierung

Wichtig: Webhook-URLs sind oeffentlich. Jeder koennte gefakte Events senden. Deswegen signieren die Absender:

- Stripe setzt Header `Stripe-Signature` mit HMAC-SHA256
- Empfaenger prueft Signatur mit Shared Secret
- Bei Mismatch: Ignorieren

Nexus validiert Stripe-Webhooks automatisch.

## Retries

Wenn dein Webhook-Endpoint nicht antwortet oder 5xx returnt, versucht der Absender es erneut - oft mit exponential backoff (1 Min, 5 Min, 30 Min, 1 Std, ...). Stripe versucht bis zu 3 Tage.

Konsequenz: dein Handler muss [idempotent](/glossar/technik-und-api/idempotenz) sein.

## Nexus-Webhooks

Zwei Richtungen:
- **Nexus empfaengt**: Stripe-Webhooks fuer Zahlungen, Subscriptions, Refunds, Disputes. Mailgun-Webhooks fuer Email-Events.
- **Nexus sendet** (in Planung): Outbound-Webhooks bei Events wie `order.paid`, `customer.created` an deine eigenen Integrationen.

## Debugging

Webhook-Logs in Stripe-Dashboard sichtbar. In Nexus unter `/manage/settings/stripe/webhooks`. Fuer lokale Entwicklung: ngrok oder Stripe CLI zum Tunneling.
