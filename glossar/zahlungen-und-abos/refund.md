---
title: Refund
order: 6
excerpt: Rueckerstattung einer Zahlung
---

# Refund

Rueckerstattung eines Zahlungsbetrags an den Kunden. Kann voll oder teilweise sein.

## Gruende

- Kunde storniert (widerruft, unzufrieden)
- Doppelzahlung versehentlich
- Technisches Problem beim Kauf
- Kulanz
- Widerrufsrecht (14 Tage DE-B2C)

## Wie in Nexus

Admin unter `/manage/orders/[id]` → "Refund"-Button. Optionen:
- Vollstaendig (gesamter Order-Betrag)
- Teilweise (Betrag eingeben)
- Optional: Grund dokumentieren

Nexus sendet Refund-Request an Stripe, wartet Bestaetigung, markiert Order als `REFUNDED` oder `PARTIALLY_REFUNDED`.

## Stripe-Terminologie

Im Stripe-Dashboard zwei Varianten:

**"Rueckbuchung"** - Authorization Reversal. Geht nur wenn Zahlung noch nicht settled ist (wenige Stunden bis 1 Tag nach Zahlung). Geld ist beim Kunden in Minuten. Taucht oft gar nicht auf der Abrechnung auf.

**"Zurueckerstattet"** - klassischer Refund. Zahlung ist schon settled. Dauert 5-10 Werktage bis Geld beim Kunden ist.

**Nexus macht in beiden Faellen denselben API-Call** (`POST /v1/refunds`). Stripe entscheidet intern welcher Weg.

## Credit Note

Bei Refund wird automatisch eine Gutschrift (Credit Note) erzeugt. Gegenbuchung zur Invoice. GoBD-konform fuer die Buchhaltung.

## Netto/Brutto-Aufteilung

Seit v1.3.85:
- `refundedAmount` - Brutto-Summe der Rueckerstattungen
- `refundedSubtotal` - Netto-Anteil der Rueckerstattung
- `refundedTax` - Steuer-Anteil der Rueckerstattung

Proportional verteilt auf Basis der urspruenglichen Order-Anteile. Fuer DATEV-Export und Finanzreports relevant.

## Subscription-Refund

Bei Abo: refund der letzten Zahlung optional. Subscription selbst wird nicht automatisch gekuendigt (das ist separater Schritt).

## Chargeback vs Refund

- **Refund** - freiwillig durch dich
- **Chargeback** - Kunde fordert Geld bei seiner Bank zurueck ohne Absprache

Chargebacks sind teurer (Stripe-Gebuehren) und schaden Score. Guter Support + Self-Service-Refund im Customer-Portal reduzieren Chargebacks.
