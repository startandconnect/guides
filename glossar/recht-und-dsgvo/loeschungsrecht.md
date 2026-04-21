---
title: Loeschungsrecht
order: 10
excerpt: Das Recht vergessen zu werden
---

# Loeschungsrecht (DSGVO Artikel 17)

Betroffene haben das Recht, die Loeschung ihrer personenbezogenen Daten zu verlangen. Auch bekannt als "Right to be Forgotten".

## Wann darf Kunde Loeschung fordern

- Daten sind fuer den urspruenglichen Zweck nicht mehr noetig
- Einwilligung wurde widerrufen (und keine andere Rechtsgrundlage)
- Betroffener legt Widerspruch ein gegen berechtigtes Interesse
- Daten wurden unrechtmaessig verarbeitet
- Loeschung ist gesetzliche Verpflichtung (z.B. nach Aufbewahrungsfrist)

## Wann musst du NICHT loeschen

- Wenn gesetzliche Aufbewahrungspflicht besteht (GoBD, Handelsrecht)
- Wenn Daten fuer Rechtsdurchsetzung noetig sind (offene Forderung, laufender Prozess)
- Wenn berechtigtes Interesse ueberwiegt (laufender Vertrag)

## Was das fuer dich bedeutet

Bei Loesch-Anfrage pruefen:
1. Ist der Kunde tatsaechlich bei dir registriert?
2. Gibt es laufende Vertraege?
3. Gibt es Buchhaltungs-Daten unter 10 Jahre alt?

Wenn Loeschung moeglich: innerhalb 30 Tage umsetzen.

Wenn nur teilweise: konkret erklaeren was wann geloescht wird und was warum nicht.

## Pseudonymisierung statt Loeschung

Bei GoBD-pflichtigen Buchhaltungs-Daten: Kundenname + Email durch "Anonymisiert / geloeschter Kunde" ersetzen, aber Buchungssatz erhalten.

Der Kunde ist dann nicht mehr identifizierbar, aber die Rechnung bleibt im System.

## Was NICHT loeschen

- Invoices und Credit Notes (GoBD, 10 Jahre)
- Transaktions-Daten bei laufender Gewaehrleistung
- Aufgezeichnete Audit-Logs (Security-relevant)
- Email-Archive wenn geschaeftlich relevant

## Was loeschen

- Marketing-Daten (Newsletter-Historie alt, Tracking-Logs)
- Nicht-mehr-noetige Profilinformationen
- Duplikate
- Temporaere Dateien

## Nexus-Tooling

Admin unter Customer-Detail → "Kunde loeschen". Gibt drei Optionen:
- **Voll-Loeschung**: nur wenn keine Orders/Invoices - bei echt-privaten Test-Kunden
- **Anonymisierung**: Personendaten ersetzen, Orders bleiben - Standardfall bei realen Kunden
- **Export fuer Transfer**: JSON mit allen Daten + dann Anonymisierung

## Self-Service im Customer-Portal

Kunde kann unter `/customer/account` selber Loeschung beantragen. Admin bekommt Notification, entscheidet (bei automatisch-eigenen Accounts ohne Kaeufe geht das direkt, bei Kaeufen muss Admin pruefen).

## Dokumentation

Jede Loesch-/Anonymisierungs-Aktion wird im Audit-Log dokumentiert:
- Wer hat es gemacht (Admin oder Kunde-selber)
- Wann
- Was wurde geloescht, was blieb

Wichtig fuer DSGVO-Rechenschaftspflicht.

## Social-Media-Plattform-Unterschied

Auf deiner Nexus-Instance kannst du Daten loeschen. Aber wenn der Kunde auch auf deiner Facebook-Seite kommentiert hat, musst du dich an Facebook wenden - liegt ausserhalb deiner Kontrolle.
