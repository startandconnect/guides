---
title: GoBD
order: 9
excerpt: Grundsaetze zur ordnungsmaessigen Buchfuehrung
---

# GoBD (Grundsaetze zur ordnungsmaessigen Fuehrung)

Deutsche Regeln fuer elektronische Buchfuehrung. Definieren wie Rechnungen, Belege, Buchungen digital zu archivieren sind. Wichtig fuer Finanzamt-Pruefungen.

## Kern-Anforderungen

- **Unveraenderbarkeit** - einmal gebucht, nicht mehr editierbar. Korrekturen nur ueber Stornobuchung.
- **Nachvollziehbarkeit** - jeder Buchungsvorgang muss rekonstruierbar sein (wer hat wann was gebucht)
- **Vollstaendigkeit** - alle Geschaeftsvorfaelle erfasst
- **Richtigkeit** - Daten entsprechen dem tatsaechlichen Vorfall
- **Zeitliche Erfassung** - Buchung zeitnah, nicht Monate spaeter
- **Ordnung** - systematische Ablage
- **Lesbarkeit** - jederzeit maschinell auswertbar

## Aufbewahrungsfristen

- **Rechnungen**: 10 Jahre
- **Handelsbuecher und Jahresabschluesse**: 10 Jahre
- **Geschaeftsbriefe**: 6 Jahre
- **Lohn-Unterlagen**: 6 Jahre

In elektronischer Form speichern (Papier-Ausdrucke sind **nicht mehr ausreichend** nach GoBD).

## Was das fuer Nexus bedeutet

- Invoices werden dauerhaft gespeichert, nicht geloescht
- Audit-Log protokolliert jede Aenderung mit Zeitstempel + User
- Refunds ueber Credit Notes (Storno-Buchung), nie durch Edit der Original-Invoice
- Rechnungs-PDFs als Snapshot-Dokumente mit Hash-Signatur

## Datev-Export

Fuer Steuerberater: Nexus hat DATEV-kompatiblen Export-Report unter `/manage/reports/finance`. CSV-Format das direkt in DATEV einlesbar ist.

## Bei Loeschung von Kundendaten

DSGVO Artikel 17 sagt "Recht auf Loeschung". GoBD sagt "10 Jahre Aufbewahrung". Konflikt!

**Loesung**: Pseudonymisierung statt echter Loeschung. Kundendaten werden anonymisiert (Name wird zu "Anonymisiert", Email gehasht), aber Buchhaltungs-Datensatz bleibt erhalten.

Nexus unterstuetzt diesen Modus. Kein echter DELETE, sondern Anonymisierungs-Flag.

## Bei Finanzamt-Pruefung

Pruefer darf deine Systeme inspizieren (Datenzugriffsrecht nach Paragraph 147 Abs 6 AO). Du musst:
- Zugang geben zu allen Buchhaltungs-Systemen
- Export-Moeglichkeit zeigen
- Einsichts-Rechte einraeumen

Nexus bietet Admin-Audit-Zugang fuer Pruefer via temporaeren Account.

## Verstoesse

Nicht-GoBD-konforme Buchfuehrung kann zur Versagung der Buchfuehrung fuehren → Schaetzungen durch Finanzamt → typisch hoehere Steuerlast + Zinsen + evtl. Ordnungsgeld.

Kleine Verstoesse werden bei Erstfeststellung meist geduldet, Wiederholung wird teuer.

## Relevanz fuer Kleinunternehmer

Auch als Kleinunternehmer GoBD-Pflicht. Auch wenn du keine USt-Voranmeldung machst: Einkommensteuer-Buchfuehrung unterliegt GoBD.
