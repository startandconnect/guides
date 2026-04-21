---
title: Zahlungen und Abos
order: 5
excerpt: Stripe, Subscription, Invoice, Coupon, Refund
---

# Zahlungen und Abos

## Stripe

Der Zahlungsanbieter, mit dem Nexus integriert ist. Nimmt Kreditkarten, SEPA, Apple Pay, Google Pay, Klarna, PayPal entgegen. Nexus synct Produkte, Kunden, Subscriptions und Invoices mit deinem Stripe-Account.

## Subscription (Abo)

Wiederkehrender Kauf. Monatlich, quartalsweise, halbjaehrlich oder jaehrlich. Stripe rechnet automatisch ab, Nexus aktualisiert den Status (`active`, `paused`, `canceled`, `trial`).

## Billing Interval

Rhythmus der Abo-Abrechnung. Nexus unterstuetzt: `WEEKLY`, `MONTHLY`, `QUARTERLY` (3 Monate), `HALF_YEARLY` (6 Monate), `YEARLY` (12 Monate).

## Invoice (Rechnung)

Offizielles Dokument einer bezahlten oder offenen Zahlung. Enthaelt Netto, Steuer, Brutto, Umsatzsteuer-ID, Zahlungsdatum. Nexus erstellt Invoices automatisch nach bezahlter Order, versendet als PDF.

## Credit Note (Gutschrift)

Gegenbuchung einer Invoice. Wird bei Refund, Storno oder Rechnungskorrektur erstellt. In Nexus als `creditNoteId` an die Order gekoppelt.

## Refund

Rueckerstattung eines Zahlungsbetrags. Kann voll oder teilweise sein. In Nexus via "Order > Refund" ausloesbar, wird an Stripe weitergereicht.

## Rueckbuchung vs Zurueckerstattet (Stripe-Terminologie)

Beides sind normale Refunds, keine Chargebacks:

- **Rueckbuchung**: Authorization Reversal (innerhalb weniger Stunden nach Zahlung). Geld ist beim Kunden in Minuten.
- **Zurueckerstattet**: klassischer Refund (Zahlung schon settled). 5-10 Werktage.

## Chargeback

Kunde beantragt Rueckbuchung bei seiner Bank, typisch bei "Ich habe das nicht gekauft" oder "Produkt nicht erhalten". Kostet dich Stripe-Gebuehren und Zeit. Nexus markiert Orders mit `dispute.status`.

## Coupon

Rabatt-Code mit festem Betrag, Prozent-Wert oder als Freebie. Kann einmalig oder wiederkehrend gelten, kann Gueltigkeitsdauer oder Max-Uses haben. In Nexus unter Produkte > Coupons.

## Trial

Kostenloser Test-Zeitraum eines Abos. Typisch 7-30 Tage. Nach Trial-Ende wird automatisch die erste Zahlung faellig. Kunde kann waehrend Trial jederzeit kuendigen.

## Tax-Inclusive vs Tax-Exclusive

- **Tax-inclusive**: Preis enthaelt bereits die Mehrwertsteuer (Standard in Deutschland B2C: 99 Euro inklusive 19 Prozent MwSt).
- **Tax-exclusive**: Steuer kommt oben drauf (typisch B2B USA: 100 Euro + tax).

Nexus unterstuetzt beide, rechnet pro Produkt/Portal-Einstellung.

## SEPA-Lastschrift

Zahlungsart fuer Europaer ueber Bankeinzug. Kunde gibt einmalig Mandat und IBAN. Stripe holt das Geld ab. Kann bis 8 Wochen nach Abbuchung per Chargeback zurueckgeholt werden.

## SCA (Strong Customer Authentication)

EU-Regulierung (PSD2), die bei Online-Zahlungen oft eine zweite Authentifizierung verlangt (3D Secure). Stripe handelt das automatisch - Kunde sieht bei Stripe-Checkout ggf. ein SMS-TAN oder App-Freigabe.

## Kleinunternehmer-Regelung (Paragraph 19 UStG)

Umsatzsteuerbefreiung fuer Selbstaendige unter 22 000 Euro Jahresumsatz. Nexus unterstuetzt in den Portal-Einstellungen "Kleinunternehmer", rechnet dann Rechnungen ohne Ausweis der Mehrwertsteuer.

## Proration

Anteilige Abrechnung bei Plan-Wechsel mitten im Zyklus. Upgrade von 10 Euro/Monat auf 20 Euro/Monat nach 15 Tagen = Kunde zahlt die Differenz fuer den Rest des Monats. Stripe berechnet automatisch.
