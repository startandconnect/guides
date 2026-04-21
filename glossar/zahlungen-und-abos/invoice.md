---
title: Invoice
order: 3
excerpt: Die Rechnung als offizielles Dokument
---

# Invoice (Rechnung)

Offizielles Dokument zu einer Zahlung. Enthaelt Netto, Steuer, Brutto, Rechnungs-Nummer, Rechnungs-Datum, Leistungsdatum und alle rechtlichen Pflichtfelder.

## Wann wird Invoice erstellt

- **Direktkauf**: sofort nach erfolgreicher Zahlung
- **Subscription**: bei jedem Billing-Zyklus automatisch
- **Refund**: zusaetzlich Credit Note

## Pflichtfelder (nach Paragraph 14 UStG)

- Name und Anschrift des leistenden Unternehmers
- Name und Anschrift des Leistungsempfaengers
- Steuernummer oder USt-IdNr
- Ausstellungsdatum
- Rechnungsnummer (fortlaufend)
- Leistungszeitraum
- Menge und Art der Leistung
- Entgelt (Netto)
- Steuersatz und Steuerbetrag
- Gesamtbetrag (Brutto)

Nexus fuellt alle diese Felder aus - du musst in den Einstellungen einmalig Unternehmensdaten hinterlegen.

## Rechnungs-Nummer

Fortlaufend, darf keine Luecken haben. Nexus nutzt Format `YYYY-NNNN` (z.B. 2026-0042). Bei Bedarf konfigurierbar.

## PDF-Generation

Nexus erzeugt bei jeder Invoice ein PDF und sendet es als E-Mail-Anhang an den Kunden. Das PDF ist auch im Customer-Portal unter `/customer/invoices/:id` downloadbar.

## Tax (Mehrwertsteuer)

Pro Invoice-Position wird Steuersatz berechnet. Nexus unterstuetzt:
- **Inclusive** (Brutto-Preis, Standard DE-B2C): "99 Euro inklusive MwSt"
- **Exclusive** (Netto-Preis, typisch B2B): "99 Euro + MwSt" = 117,81 Euro Brutto
- **Reverse-Charge** (innergemeinschaftlich): "Steuerschuldnerschaft des Leistungsempfaengers"
- **Kleinunternehmer** (Paragraph 19 UStG): "Keine Umsatzsteuer gem. Paragraph 19 UStG"

Konfigurierbar pro Portal-Setting + pro Produkt.

## Nachtraeglich aendern

Nicht zulaessig nach GoBD. Bei Fehlern: Credit Note + neue korrekte Invoice ausstellen. Nexus bietet das ueber "Invoice-Korrektur"-Flow im Admin.

## Archiv

Rechnungen muessen 10 Jahre aufbewahrt werden. Nexus speichert sie dauerhaft in der Instance-DB. Backup-Strategie ist deine Verantwortung als Nexus-Kunde.
