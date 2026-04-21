---
title: AV-Vertrag
order: 3
excerpt: Vertrag mit Dienstleistern die deine Kundendaten verarbeiten
---

# AV-Vertrag (Auftragsverarbeitungs-Vertrag)

Vertrag zwischen dir (Verantwortliche Stelle) und einem Dienstleister (Auftragsverarbeiter) der in deinem Auftrag personenbezogene Daten verarbeitet. Pflicht nach DSGVO Artikel 28.

## Wer ist Auftragsverarbeiter

Alle die in deinem Namen und nach deinen Weisungen Daten verarbeiten:

- **Hosting-Provider** (Hetzner, AWS) - speichern Kundendaten
- **SaaS-Tools** (Nexus, HubSpot, Brevo) - verarbeiten Kundendaten
- **Zahlungsanbieter** (Stripe, PayPal) - haben Kundendaten zur Zahlung
- **Email-Versand** (Mailgun, SendGrid) - schicken Mails an deine Kunden
- **CRM, Newsletter-Tools, Support-Systeme** - diverse Daten
- **Freelancer die Zugang haben** - streng genommen auch

## Pflichtinhalte

Der AV-Vertrag muss regeln:

- Zweck und Art der Verarbeitung
- Art der Daten und Betroffenen
- Pflichten des Auftragsverarbeiters
- Technisch-Organisatorische Massnahmen (TOMs)
- Sub-Auftragsverarbeiter (wer darf weiter delegieren)
- Kontroll-Rechte des Auftraggebers
- Meldepflicht bei Datenpannen
- Loeschung/Rueckgabe nach Vertragsende

## Wo beziehen

- **Nexus**: AV-Vertrag von Start und Connect auf Anfrage (Email an support@startandconnect.com)
- **Stripe**: unter stripe.com/legal/dpa
- **Hetzner**: in der Hetzner-Console selber akzeptierbar
- **Mailgun, Google, Cloudflare etc.**: alle haben Standard-DPAs online

## Nicht nur papierkram

Du bist fuer die gesamte Verarbeitungskette verantwortlich. Wenn der Subunternehmer pfuscht, kannst du trotzdem belangt werden. Deshalb:
- Dienstleister sorgfaeltig auswaehlen
- AV-Vertraege nicht nur blindunterschreiben sondern lesen
- Bei Bedarf Ruecksprache mit Datenschutz-Beauftragtem

## Nach Vertragsende

- Dienstleister muss alle Daten loeschen oder zurueckgeben
- Dokumentation der Loeschung
- Fuer Buchhaltungs-Daten: 10 Jahre Aufbewahrungspflicht (GoBD) - nicht in AV-Vertrag regelbar

## TOMs (Technisch-Organisatorische Massnahmen)

Anhang zum AV-Vertrag mit konkreten Sicherheits-Massnahmen:
- Zutrittsschutz (Serverraum)
- Zugriffskontrolle (Rollen/Passwoerter)
- Verschluesselung (HTTPS, at-rest-Encryption)
- Backup + Wiederherstellung
- Audit-Logs
- Incident-Response-Plan

Nexus-TOMs sind im AV-Vertrag dokumentiert.
