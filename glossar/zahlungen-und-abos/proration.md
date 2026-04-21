---
title: Proration
order: 13
excerpt: Anteilige Abrechnung bei Plan-Wechsel
---

# Proration

Anteilige Abrechnung bei Plan-Wechsel mitten im Abrechnungs-Zyklus. Wird typisch bei Upgrades, Downgrades oder Mengen-Aenderungen verwendet.

## Beispiel Upgrade

Kunde hat monatliches Abo 10 Euro, Abrechnung am 1. des Monats. Am 16. upgraded er auf 20 Euro/Monat.

- Ueberzahlung fuer den Rest des Monats: 10 Euro x 15/30 Tage = 5 Euro (nicht verbraucht vom alten Plan)
- Anteilige Neuzahlung fuer neuen Plan: 20 Euro x 15/30 Tage = 10 Euro
- Proration-Rechnung: 10 - 5 = **5 Euro extra sofort**

Ab naechstem Monat: voller 20 Euro-Preis regulaer.

## Beispiel Downgrade

Kunde geht von 20 Euro auf 10 Euro mid-cycle.

- Ueberzahlung 20 x 15/30 = 10 Euro Credit
- Anteil neuer Plan 10 x 15/30 = 5 Euro
- Proration-Ergebnis: 5 Euro Credit (wird auf naechste Rechnung verrechnet oder als Credit im Account)

## Beispiel Quantity-Change

Kunde hat 5 Seats zu je 10 Euro, fuegt 5 weitere dazu am 16.:

- Zusaetzliche 5 Seats x 10 Euro x 15/30 = 25 Euro sofort
- Naechster Monat: 10 Seats x 10 Euro = 100 Euro

## Wer rechnet?

Stripe macht's automatisch. Nexus sendet nur das neue Pricing, Stripe berechnet Proration und stellt eine Pro-Rata-Invoice aus.

## Konfiguration

Pro Subscription kannst du Proration-Verhalten einstellen:
- **create_prorations** (Default): neue Invoice-Items entsprechend Anteil
- **none**: kein Proration, naechster Zyklus neuer Preis
- **always_invoice**: sofortige Invoice mit Pro-Rata

In Nexus ist create_prorations Default.

## Visueller Effekt fuer Kunden

Gute Dashboards zeigen den Kunden schon beim Plan-Wechsel:
- "Neuer Preis ab naechstem Monat: 20 Euro"
- "Sofortige Abrechnung: 5 Euro"
- "Insgesamt spare Sie X bis zum Jahr"

Transparente Proration = weniger Support-Anfragen.

## Downgrade-Missbrauch

Manche Nutzer upgraden fuer 1 Tag (brauchen Feature einmalig), downgraden dann. Stripe gibt Credit fuer nicht verbrauchte Zeit. Fuer dich unerwuenscht.

Gegenmassnahme:
- **No-Proration-Downgrades** - Downgrade erst zum Periodenende wirksam
- **Minimum-Term** - Plan kann nicht in ersten X Tagen downgrade werden

Nexus-Mindestlaufzeit-Feature ist in Planung (siehe `minimum-term-plan.md`).
