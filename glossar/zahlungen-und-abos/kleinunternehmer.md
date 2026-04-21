---
title: Kleinunternehmer (Paragraph 19 UStG)
order: 11
excerpt: Umsatzsteuer-befreit bei geringem Umsatz
---

# Kleinunternehmer (Paragraph 19 UStG)

Deutsche Regelung fuer Selbststaendige und kleine Firmen mit geringem Umsatz. Du weist keine Umsatzsteuer aus, zahlst aber auch keine Vorsteuer-Abzuege.

## Voraussetzung (Stand 2024+)

- Umsatz im Vorjahr unter **22 000 Euro**
- Voraussichtlicher Umsatz im laufenden Jahr unter **50 000 Euro**

Wenn eine der Grenzen ueberschritten wird, verlierst du die Regelung zum naechsten Jahr.

## Vorteile

- Einfachere Buchhaltung (keine USt-Voranmeldung)
- Fuer Privatkunden: wirkst guenstiger (kein 19-Prozent-Zuschlag)
- Kein Vorsteuer-Abzug, aber auch kein Vorsteuer-Aufwand

## Nachteile

- Kein Vorsteuer-Abzug auf Ausgaben
- B2B-Kunden finden es oft unpraktisch (keine USt abziehbar)
- Wirkt fuer manche unprofessionell (signalisiert kleine Firma)

## Wechsel zur Regelbesteuerung

Du kannst freiwillig auf Regelbesteuerung wechseln (Verzicht auf die Kleinunternehmer-Regelung). Ist 5 Jahre bindend. Sinnvoll wenn du viele Geschaeftskunden hast oder grosse Vorsteuer-Ausgaben (z.B. Einkauf von Software, Equipment).

## In Nexus aktivieren

Unter `/manage/settings/invoice`:
- Toggle "Kleinunternehmer-Regelung"
- Standardtext auf Rechnung: "Gem. Paragraph 19 UStG wird keine Umsatzsteuer berechnet."
- Produkte werden automatisch als tax-free verkauft (kein Steueranteil in Invoices)

## Zwischen-Geschaefts-Jahre

Achtung: die 22 000 / 50 000 Grenzen gelten pro Kalenderjahr. Bei Jahr-Anfang im Juni kannst du nur anteilige Nutzung machen.

## Kombination mit Stripe

Stripe-Account muss trotzdem deutsche USt-IdNr haben (wird als Gewerbe fuer Stripe gefuehrt, auch wenn du Kleinunternehmer bist). Fuer Reverse-Charge auf Nicht-EU-Kunden wird die USt-IdNr gebraucht.

## Not-Alone-Beispiel

Das Not-Alone-Projekt startet als Kleinunternehmer. Nexus-Setup dort aktiviert, Rechnungen werden ohne USt ausgestellt.
