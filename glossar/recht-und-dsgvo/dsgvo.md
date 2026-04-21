---
title: DSGVO
order: 1
excerpt: Das europaeische Datenschutz-Grundgesetz
---

# DSGVO (Datenschutz-Grundverordnung)

EU-weit geltendes Datenschutzrecht seit Mai 2018. Regelt wie Firmen personenbezogene Daten verarbeiten muessen. Verstoesse koennen bis 20 Millionen Euro oder 4 Prozent des Jahresumsatzes kosten (je nachdem was hoeher ist).

## Kernprinzipien

- **Rechtmaessigkeit** - fuer jede Verarbeitung muss eine Rechtsgrundlage existieren (Einwilligung, Vertrag, berechtigtes Interesse etc.)
- **Zweckbindung** - Daten nur fuer den Zweck nutzen fuer den sie erhoben wurden
- **Datenminimierung** - nur soviel Daten wie noetig
- **Richtigkeit** - Daten muessen aktuell und korrekt sein
- **Speicherbegrenzung** - Daten nur so lange wie noetig aufbewahren
- **Integritaet und Vertraulichkeit** - Daten muessen geschuetzt sein
- **Rechenschaftspflicht** - du musst beweisen koennen dass du DSGVO befolgst

## Rechte der Betroffenen

- **Auskunft** - "welche Daten habt ihr von mir"
- **Berichtigung** - "das ist falsch, bitte korrigieren"
- **Loeschung** - "loeschen Sie meine Daten"
- **Einschraenkung** - "legen Sie meine Daten erstmal auf Eis"
- **Datenuebertragbarkeit** - "gebt mir meine Daten als JSON-Export"
- **Widerspruch** - "nutzt meine Daten nicht mehr fuer X"

Nexus hat Tools fuer alle sechs Rechte (im Customer-Portal + Admin).

## Was musst du dokumentieren

- **Verzeichnis von Verarbeitungstaetigkeiten** - welche Daten verarbeitest du, wofuer, wie lange, mit welcher Basis
- **AV-Vertraege** mit allen Dienstleistern (Nexus, Stripe, Mailgun, Hosting, etc.)
- **Datenschutzerklaerung** aktuell halten
- **Techn.-Organisator. Massnahmen** (TOMs) - wie schuetzt du die Daten

## Nexus und DSGVO

- Server in Deutschland (Hetzner)
- Jede Kunden-Instance mit eigener DB (Daten-Trennung per Design)
- AV-Vertrag von SAC auf Anfrage
- Cookie-Banner eingebaut
- Double-Opt-In fuer Newsletter
- Export/Loesch-Rechte als Features

## Boete-Risiko einschaetzen

Bei kleineren Firmen (<50 Mitarbeiter) realistisch: Abmahnung von Datenschutz-Beauftragten, Nachbesserung verlangt. Millionenstrafen treffen primaer Konzerne mit eklatanten Verstoessen.

Trotzdem: compliance-orientiert arbeiten. Reputations-Schaden ist schlimmer als finanzielle Strafe.
