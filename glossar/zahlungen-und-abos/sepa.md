---
title: SEPA-Lastschrift
order: 10
excerpt: Bankeinzug in Europa
---

# SEPA-Lastschrift

Zahlungsart fuer Europa per Bankkonto. Kunde gibt einmalig sein IBAN und Mandat, Stripe holt das Geld ab.

## Vorteile

- **Niedrigere Gebuehren** als Kreditkarte (0,35 Euro flat statt 1,5 Prozent + 0,25)
- **Hoehere Annahme-Rate** - Kreditkarten werden manchmal abgelehnt, Lastschrift fast nie
- **Von Deutschen bevorzugt** - Kulturell etablierte Zahlungsart
- **Wiederkehrende Zahlungen unkompliziert** - Mandat einmal, Einzug beliebig oft

## Nachteile

- **Langsamer** - Stripe braucht 3-5 Werktage bis Geld bei dir ist
- **Kann bis 8 Wochen zurueckgebucht werden** - SEPA-Kunden-Schutz
- **Ausschliesslich Europa** - US-Kunden brauchen ACH oder Card

## Chargeback-Aequivalent: SEPA-Reversal

Kunde kann innerhalb 8 Wochen bei der Bank "Rueckbuchung" beantragen - oft ohne Grund-Angabe. Geld geht automatisch zurueck, du bekommst Webhook.

Nexus handelt SEPA-Reversals:
- Subscription geht in `PAUSED` oder `FAILED`
- Customer bekommt Email "Zahlung wurde zurueckgebucht"
- Admin wird benachrichtigt
- Dunning-Retry startet

## Mandat

Einmalige Einwilligung des Kunden. Elektronisches Mandat (eMandate) ist SEPA-konform. Nexus verwaltet das ueber Stripe automatisch.

Mandat ist gueltig bis der Kunde es widerruft oder 36 Monate ohne Nutzung ablaufen.

## Fuer Nexus-Kunden

Du musst in den Stripe-Einstellungen SEPA aktivieren (standardmaessig an fuer deutsche Konten). Im Checkout erscheint SEPA dann als Option neben Kreditkarte.

## Eignung

- **Einmalkauf**: eher nicht (Settlement-Zeit zu lang, Kunde will Download sofort)
- **Subscription**: sehr gut - monatlich oder jaehrlich, keine Dringlichkeit
- **Teure Einzelkaeufe**: Rechnung statt Lastschrift oft besser
