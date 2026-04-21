---
title: Widerrufsrecht
order: 7
excerpt: 14 Tage Rueckgabe fuer Verbraucher
---

# Widerrufsrecht

14 Tage Widerruf fuer Verbraucher-Kaeufe nach Fernabsatz (also alle Online-Kaeufe). Gesetzlich verpflichtend, nicht verhandelbar bei B2C.

## Wie funktioniert's

Kunde kauft → hat 14 Tage Zeit den Kauf zu widerrufen → du musst den Kaufpreis zurueckerstatten.

Frist beginnt:
- Bei physischen Produkten: Tag nach Erhalt
- Bei digitalen Produkten: Tag nach Vertragsschluss

## Widerrufsbelehrung

Du musst den Kunden ueber sein Widerrufsrecht aufklaeren. Musterformulierung im EGBGB Anlage 1. Nexus hat den Standardtext eingebaut.

Wenn du die Belehrung nicht korrekt machst, verlaengert sich die Widerrufsfrist auf **12 Monate und 14 Tage**. Also sorgfaeltig.

## Verzicht auf Widerrufsrecht bei digitalen Gueter

Bei digitalen Produkten (Kurse, Ebooks, Software) kann Widerrufsrecht VOR Leistungserbringung verwirkt werden - aber nur mit expliziter aktiver Zustimmung des Kunden.

**Typischer Checkbox-Text:**
> "Ich stimme ausdruecklich zu, dass Sie mit der Ausfuehrung des Vertrags vor Ablauf der Widerrufsfrist beginnen. Mir ist bewusst, dass ich mein Widerrufsrecht mit Beginn der Ausfuehrung verliere."

Nexus-Checkout hat diesen Zusatz-Flow als Option pro Produkt konfigurierbar.

## Ohne Verzicht

Wenn Kunde NICHT verzichtet, behaelt er 14 Tage Widerrufsrecht - auch wenn er den Kurs schon konsumiert hat. Du musst bei Widerruf zurueckzahlen, nur anteilig reduziert fuer die schon konsumierte Zeit.

## Was NICHT widerruffaehig ist

- Individuell angefertigte Ware (z.B. personalisierte Produkte)
- Verderbliche Ware (nicht Nexus-relevant)
- Zeitungen, Magazine, Zeitschriften (Ausnahme: Abos)
- Hygiene-versiegelte Ware (z.B. Kosmetik nach Oeffnung)
- Dienstleistungen nach kompletter Erfuellung mit Vorab-Zustimmung

## B2B-Ausnahme

Fernabsatz-Widerrufsrecht gilt nur Verbraucher (Privatpersonen). Gewerbliche Kunden haben kein gesetzliches Widerrufsrecht.

**Achtung:** Du musst im Checkout erkennen ob B2B oder B2C. Wenn nur "Vorname/Nachname" abgefragt wird: automatisch B2C. Wenn Firmenname erlaubt: B2B moeglich.

## Rueckzahlungspflicht

- Innerhalb 14 Tagen nach Widerrufs-Erklaerung
- Ueber den gleichen Zahlungsweg wie der Kauf
- Ohne zusaetzliche Kosten fuer den Kunden

## Nexus-Support

Bei Widerruf: Admin-Flow unter Order → Refund mit Grund "Widerruf". Nexus erzeugt Credit Note + Stripe-Refund automatisch.
