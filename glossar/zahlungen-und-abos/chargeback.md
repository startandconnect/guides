---
title: Chargeback
order: 7
excerpt: Wenn der Kunde bei seiner Bank das Geld zurueckfordert
---

# Chargeback

Kunde beantragt Rueckbuchung bei seiner Bank oder Kreditkarten-Firma - ohne mit dir zu sprechen. Fuer dich als Verkaeufer ein teures Aergernis.

## Typische Gruende

- **Fraud** - "Meine Karte wurde missbraucht" (klassisch Chargeback-Reason Code 4837)
- **Product not received** - "Ich habe nichts bekommen"
- **Not as described** - "Es war nicht wie beschrieben"
- **Unauthorized subscription** - "Ich wusste nicht dass das Abo ist"

## Was dich das kostet

- **Refund-Betrag** - Kunde kriegt sein Geld
- **Stripe-Chargeback-Fee**: 15 Euro pro Vorgang (nicht erstattet wenn du gewinnst)
- **Admin-Zeit** - du musst antworten, Dokumente hochladen
- **Score-Effekt** - zu viele Chargebacks = Stripe markiert dich als Risiko-Account, hoehere Gebuehren oder Sperrung

## Prozess

1. Kunde ruft Bank an oder beantragt online
2. Kredit-Netzwerk informiert Stripe
3. Stripe informiert dich (Webhook `charge.dispute.created`)
4. Du hast typisch 7-14 Tage Zeit zu antworten mit Beweisen:
   - Rechnung mit Lieferadresse
   - Tracking (bei physisch - bei digital oft schwer)
   - Screenshots der AGB-Zustimmung
   - Download-Logs (hat der Kunde die Datei runtergeladen?)
   - Email-Kommunikation
5. Bank entscheidet. Gewinnst du: Geld zurueck. Verlierst du: Refund plus Fee.

## Nexus-Support

Seit v1.2.x hat Nexus ein Dispute-Panel:
- Webhook `charge.dispute.created` wird empfangen
- Order bekommt Flag `dispute.status = 'needs_response'`
- Admin-Notification mit Deadline
- Upload-Feld fuer Evidence-Dokumente
- Stripe-Dispute-Metadata in der Order sichtbar

## Chargeback-Rate

Kreditkarten-Netzwerke haben Limits:
- **Unter 0,75 Prozent**: normal
- **0,75-1 Prozent**: Beobachtungs-Status
- **Ueber 1 Prozent**: Risiko-Account, hoehere Gebuehren oder Kuendigung

Ein Chargeback pro 1000 Transaktionen ist unproblematisch. Mehr als 10 pro 1000 = Alarmstufe.

## Praevention

- **Klarer Kauf-Prozess** - keine dunklen Muster, transparente AGB
- **Sichtbare Abo-Hinweise** - Kunde weiss dass es wiederkehrt
- **Guter Support** - schnell antworten, kulanter Refund
- **Self-Service-Cancel** - Kunde kann selber kuendigen (kein "rufen Sie an")
- **Impressum + Kontakt** - Kunde findet dich wenn er Problem hat

Ein freiwilliger Refund ist immer billiger als ein verlorener Chargeback.
