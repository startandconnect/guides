---
title: Trigger
order: 13
excerpt: Das Event, das eine Automation startet
---

# Trigger

Ein Event, das eine Automation oder Delivery-Action-Kette ausloest. Das "Wenn" in der "Wenn-Dann"-Logik.

## Typische Trigger in Nexus

| Trigger | Wann | Genutzt fuer |
|---|---|---|
| `PURCHASE` | Order bezahlt | Willkommens-Mail, Zugang freischalten |
| `TRIAL_STARTED` | Trial begonnen | Onboarding-Mails |
| `TRIAL_ENDED` | Trial vorbei (egal ob Kauf oder nicht) | Nachfass-Mail, Feedback-Bitte |
| `SUBSCRIPTION_CREATED` | Abo gestartet | Zugang freischalten, Bestaetigung |
| `SUBSCRIPTION_RENEWED` | monatliche Verlaengerung erfolgreich | Dankesnachricht |
| `SUBSCRIPTION_CANCELED` | Kunde kuendigt | Offboarding, Win-Back-Angebot |
| `SUBSCRIPTION_ENDED` | Abo tatsaechlich beendet (nach Ablauf) | Zugang sperren |
| `PAYMENT_FAILED` | Zahlung fehlgeschlagen | Warnmail, Dunning |
| `REFUND` | Geld zurueck | Follow-Up, Zugang sperren |
| `BEFORE_EVENT` | X Stunden/Tage vor Event | Reminder |
| `AFTER_EVENT` | nach Event | Nachbereitung, Feedback |
| `FORM_SUBMITTED` | Kontaktformular abgeschickt | Lead-Bestaetigung |
| `NEWSLETTER_SUBSCRIBED` | DOI bestaetigt | Welcome-Series |
| `TAG_ADDED` | Kunde bekommt ein Tag | Segmente-spezifische Aktionen |

## Wie Trigger intern funktionieren

Nexus hat einen [Event-Bus](/glossar/technik-und-api/webhook) (intern `publishLogAppended` etc.). Wenn ein Event passiert, wird es im Bus veroeffentlicht. Scheduler prueft welche Automations auf den Event reagieren und plant Executions ein.

## Custom Trigger

Plugins koennen eigene Trigger anbieten:
- `events-plugin` liefert `EVENT_BOOKED`, `EVENT_CANCELED`, `EVENT_REMINDER_SENT`
- `forms-plugin` liefert `FORM_SUBMITTED`
- `chatbot` liefert `CHAT_STARTED`, `CHAT_CONVERSION`

## Trigger-Filtering

Du kannst Trigger verfeinern:
- Nur fuer bestimmtes Produkt
- Nur fuer bestimmte Coupon-Codes
- Nur wenn Order-Wert ueber X
- Nur fuer bestimmte Kunden-Tags

Beispiel: "WELCOME_EMAIL nur fuer Orders ueber 100 Euro, Produkt-Kategorie 'Premium'".

## Zeit-basierte Trigger

`BEFORE_EVENT` und `WAIT` sind time-based. Der Scheduler laeuft minuetlich, prueft faellige Executions und feuert sie ab. Praezision: auf Minute genau.
