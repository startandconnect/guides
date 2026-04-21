---
title: Credit Note
order: 15
excerpt: Die Gutschrift als Gegenbuchung zur Rechnung
---

# Credit Note (Gutschrift)

Gegenbuchung zu einer Invoice. Wird bei Refund, Storno oder Rechnungs-Korrektur erstellt. GoBD-konform fuer die Buchhaltung.

## Wann

- **Refund** - Kunde bekommt Geld zurueck. Credit Note = negative Rechnung.
- **Storno** - Auftrag wurde storniert, urspruengliche Invoice muss "aufgehoben" werden.
- **Rechnungs-Korrektur** - Invoice hat falschen Betrag, muss storniert + neu ausgestellt werden.

## Pflichtangaben

Wie Invoice, plus:
- Verweis auf urspruengliche Invoice-Nummer
- Grund fuer Credit Note
- Negativer Betrag (fuer Rechnungswesen)

## In Nexus

Bei jedem Refund erstellt Nexus automatisch eine Credit Note. Gespeichert als `creditNoteId` an der Order.

Credit Note kann als PDF heruntergeladen werden - unter `/customer/invoices/:id` beim Kunden und `/manage/invoices/:id` beim Admin.

## GoBD-Konformitaet

Rechnungen und Credit Notes duerfen nicht veraendert werden nach Erstellung. Nexus speichert sie als immutable Records. Aenderungen am Order-Status fuehren immer zu neuen Credit Notes, nie zu Edits bestehender Dokumente.

## Unterschied zu Refund

- **Refund** ist die **Zahlungs-Aktion** (Geld zurueck an Kunde)
- **Credit Note** ist das **Buchhaltungs-Dokument** (negative Rechnung)

In der Regel gehoeren die zusammen: Refund triggert Credit Note. Aber Credit Note kann auch ohne Refund sein (z.B. wenn Kunde noch gar nicht gezahlt hat, nur storniert).

## Rechnungs-Korrektur-Flow in Nexus

Admin unter Order-Detail → "Rechnung korrigieren":
1. Nexus erstellt Credit Note fuer alte Invoice (storniert sie praktisch)
2. Admin editiert die Korrektur-Daten
3. Nexus erstellt neue Invoice mit korrektem Betrag
4. Kunde bekommt beide Dokumente per Email

Sieht fuer Kunde so aus: "Ihre Rechnung wurde korrigiert, hier sind die Dokumente".

## DATEV-Export

Finanzreport-Export in Nexus trennt sauber:
- Invoices als positive Betraege
- Credit Notes als negative Betraege
- Netto-Umsatz = Summe aller

Steuerberater kann das direkt importieren.
