---
title: Recht und DSGVO
order: 6
excerpt: DSGVO, Double-Opt-In, AV-Vertrag, Impressum
---

# Recht und DSGVO

## DSGVO (Datenschutz-Grundverordnung)

EU-weit geltendes Datenschutzrecht seit 2018. Regelt, wie Firmen personenbezogene Daten verarbeiten muessen. Kernprinzipien: Einwilligung, Zweckbindung, Datenminimierung, Transparenz, Rechte der Betroffenen.

Nexus ist DSGVO-konform gebaut: lokale Google-Fonts, Cookie-Banner, Double-Opt-In, Export/Loeschung-Rechte fuer Kunden, serverseitige Speicherung in Deutschland.

## Double-Opt-In (DOI)

Zwei-Stufen-Bestaetigung fuer Newsletter-Anmeldungen: Kunde gibt Email an, bekommt Bestaetigungsmail mit Link, klickt Link = erst dann ist er wirklich Abonnent. Pflicht fuer rechtssichere Email-Werbung in Deutschland.

Nexus Newsletter-Plugin hat DOI eingebaut.

## AV-Vertrag (Auftragsverarbeitungs-Vertrag)

Vertrag zwischen dir als verantwortlicher Stelle und einem Dienstleister, der in deinem Auftrag personenbezogene Daten verarbeitet (z.B. Nexus, Stripe, Mailgun). Pflicht nach DSGVO Artikel 28.

Start und Connect liefert den AV-Vertrag fuer Nexus auf Anfrage.

## Impressum

Pflicht-Angabe fuer geschaeftliche Websites nach Telemediengesetz (TMG). Muss Name, Adresse, Kontakt, Handelsregister (falls vorhanden), UStID enthalten. In Nexus konfigurierbar unter Einstellungen > Legal, wird automatisch im Footer verlinkt.

## Datenschutzerklaerung

Pflicht-Dokument nach DSGVO Artikel 13/14, das alle Verarbeitungen personenbezogener Daten erklaert. Welche Daten werden wann und wozu verarbeitet. Nexus hat Template + Content-Editor.

## AGB (Allgemeine Geschaeftsbedingungen)

Vertragsbedingungen fuer Kaeufe. Muessen vor Kauf sichtbar sein, Kunde muss zustimmen. Nexus-Checkout zwingt AGB-Zustimmung.

## Widerrufsrecht

14 Tage Widerruf fuer Verbraucher-Kaeufe nach Fernabsatzgesetz. Bei digitalen Produkten kann mit expliziter Zustimmung ("Ich verzichte auf mein Widerrufsrecht") verkuerzt werden. Nexus bietet den Checkbox-Flow.

## Cookie-Banner

Einwilligungs-Dialog, der Nutzern die Wahl gibt welche Cookies/Tracking-Services sie erlauben. Pflicht fuer alle nicht-essentiellen Cookies (Analytics, Marketing). Nexus hat Banner eingebaut, konfigurierbar pro Portal.

## Opt-In vs Opt-Out

- **Opt-In**: Nutzer muss aktiv zustimmen. In der EU Standard fuer Marketing-Cookies.
- **Opt-Out**: Tracking laeuft standardmaessig, Nutzer muss widersprechen. In der EU nur fuer essentielle Cookies.

## Consent Mode

Google-Analytics-Feature, das Tracking nur durchfuehrt wenn Nutzer zugestimmt hat. Nexus setzt Consent Mode automatisch basierend auf Cookie-Banner-Entscheidung.

## PII (Personally Identifiable Information)

Personenbezogene Daten: Name, Email, Adresse, IP, alles was einen Menschen identifizierbar macht. Aus DSGVO-Sicht besonders schuetzenswert. Nexus verschluesselt sensible Felder.

## Recht auf Loeschung

Kunde kann jederzeit Loeschung seiner Daten fordern (DSGVO Artikel 17). Nexus hat Loesch-Funktion im Customer-Portal und im Admin. Einschraenkung: Buchhaltungs-Daten muessen 10 Jahre aufbewahrt werden (GoBD).

## Recht auf Datenuebertragbarkeit

Kunde kann alle seine Daten strukturiert exportiert bekommen (DSGVO Artikel 20). Nexus hat JSON-Export pro Kunde in Planung.

## GoBD (Grundsaetze zur ordnungsmaessigen Fuehrung)

Deutsche Regeln zur elektronischen Buchfuehrung. Rechnungen muessen 10 Jahre unveraendert aufbewahrt werden. Nexus nutzt audit-log-basierte Unveraenderlichkeit fuer Invoices.

## Server-Standort Deutschland

Alle Nexus-Instanzen liegen bei Hetzner in Deutschland (Nuernberg / Falkenstein). Keine Datenuebertragung in die USA. Relevant fuer DSGVO-Konformitaet und Kunden-Vertrauen.
