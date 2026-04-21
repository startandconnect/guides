---
title: Subscription
order: 2
excerpt: Wiederkehrende Zahlungen
---

# Subscription (Abo)

Wiederkehrender Kauf. Kunde zahlt in definiertem Rhythmus, bekommt dafuer dauerhaft Zugang zu einem Produkt oder Service.

## Rhythmus

Nexus unterstuetzt:
- **WEEKLY** - woechentlich (selten)
- **MONTHLY** - monatlich (Standard)
- **QUARTERLY** - alle 3 Monate
- **HALF_YEARLY** - alle 6 Monate
- **YEARLY** - jaehrlich

Gaengig fuer Kurse/Memberships: Monthly + Yearly (oft mit Rabatt). Fuer B2B-Tools: Quarterly + Annual.

## Lifecycle

- **CREATED** - Kauf abgeschlossen
- **TRIAL** - Trial-Zeitraum laeuft
- **ACTIVE** - zahlend
- **PAUSED** - voruebergehend pausiert (Payment failed, Urlaubs-Pause)
- **CANCELED** - Kunde hat gekuendigt (laeuft noch bis currentPeriodEnd)
- **ENDED** - Subscription nicht mehr aktiv

## Kuendigung

Standard: zum Ende der laufenden Periode. Kunde kuendigt im Januar, Abo laeuft bis Ende Januar (monatlich) oder Ende Dezember (jaehrlich).

Sofortige Kuendigung mit Proration (anteilige Rueckerstattung) ist moeglich aber nicht default in Nexus.

## Proration

Wenn Kunde mitten im Zyklus das Produkt wechselt oder Menge aendert: anteilige Abrechnung. Upgrade von 10/Monat auf 20/Monat nach 15 Tagen = Kunde zahlt 5 Euro Differenz fuer die Rest-Periode. Stripe rechnet automatisch.

## Subscription in Nexus

Pro Kunde im Customer-Portal unter `/customer/subscriptions`. Kunde sieht Status, naechstes Billing-Datum, Kuendigungsoption.

Admin im Admin-Bereich unter `/manage/subscriptions`. Kann Stati manuell aendern, Refunds triggern, Kommentare dranhaengen.

## Failed Payment Handling

Wenn Kreditkarte abgelaeuft oder abgelehnt wird:
- Stripe versucht mehrfach (Dunning, typisch 4 Retries ueber 3 Wochen)
- Parallel bekommt Kunde Email "bitte Zahlungsdaten aktualisieren"
- Nexus zeigt Warn-Banner im Customer-Portal
- Nach finalem Fail: Subscription wird als PAUSED oder ENDED markiert

Details pro Dunning-Flow konfigurierbar. Siehe Payment-Failure-System (v1.2.264+).
