---
title: Billing Interval
order: 4
excerpt: Wie oft ein Abo abgerechnet wird
---

# Billing Interval

Rhythmus in dem ein Abo abgerechnet wird. Nexus unterstuetzt 5 Varianten.

## Die 5 Nexus-Intervalle

| Enum-Wert | Bedeutung | Typischer Use-Case |
|---|---|---|
| `WEEKLY` | woechentlich | Selten, meist nur Mitgliedschaften mit starker Aktivitaet |
| `MONTHLY` | monatlich | Standard fuer B2C und SaaS |
| `QUARTERLY` | alle 3 Monate | Mittlere Bindung, weniger Payment-Friction |
| `HALF_YEARLY` | alle 6 Monate | Selten, zwischen monthly und yearly |
| `YEARLY` | jaehrlich | Meist mit 2 Monaten Rabatt gegenueber monthly |

## Stripe-Mapping

Nexus kommuniziert mit Stripe ueber `recurring.interval` + `recurring.interval_count`:

| Nexus | Stripe |
|---|---|
| WEEKLY | interval=week, count=1 |
| MONTHLY | interval=month, count=1 |
| QUARTERLY | interval=month, count=3 |
| HALF_YEARLY | interval=month, count=6 |
| YEARLY | interval=year, count=1 |

## Rabatte pro Intervall

Typisches Muster:
- Monthly: 29 Euro
- Quarterly: 75 Euro (entspricht 25 Euro/Monat, 14 Prozent Rabatt)
- Yearly: 290 Euro (entspricht 24 Euro/Monat, 17 Prozent Rabatt)

Laengere Bindung = niedrigerer Preis. Vorteil fuer dich: niedrigeres Churn, hoeherer LTV.

## MRR-Berechnung

MRR-Zahl wird pro Subscription berechnet:
- Monthly: `amount` direkt
- Quarterly: `amount / 3`
- Half-Yearly: `amount / 6`
- Yearly: `amount / 12`

So wird der MRR ueber alle Abos vergleichbar, egal welchen Rhythmus sie haben.

## Wechsel zwischen Intervallen

Kunde upgraded von Monthly auf Yearly: Nexus kuendigt die Monthly-Subscription und erstellt Yearly. Optional mit Proration (Credit fuer Rest-Monat). Konfigurierbar.

## Eine wichtige Schwachstelle

QUARTERLY-Case fehlte in `buildStripePriceParams` bis Sprint 8 (2026-04-19). Neue QUARTERLY-Produkte wurden beim Stripe-Push als `month/1` statt `month/3` angelegt. Fix in v1.3.75. Existierende Produkte waren nicht betroffen (Stripe-Prices sind immutable, Rechnungen korrekt).
