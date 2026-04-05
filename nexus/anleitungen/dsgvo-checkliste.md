---
title: DSGVO-Checkliste
order: 9
excerpt: DSGVO-Konformität sicherstellen mit praktischer Checkliste
---

# DSGVO-Checkliste

Datenschutz ist in Deutschland kein Nice-to-have, sondern Pflicht. Die gute Nachricht: Nexus bringt viele DSGVO-Features von Haus aus mit. Deutsche Server, lokale Fonts, IP-Anonymisierung. Hier gehst du Punkt für Punkt durch, was du einrichten musst.

## Übersicht

| Nr. | Anforderung | Nexus-Feature | Status |
|-----|-------------|--------------|--------|
| 1 | Impressum | Legal-Seiten | ☐ |
| 2 | Datenschutzerklärung | Legal-Seiten | ☐ |
| 3 | AGB | Legal-Seiten | ☐ |
| 4 | Cookie Consent | Integriert | ☐ |
| 5 | Analytics datenschutzkonform | IP-Anonymisierung | ☐ |
| 6 | Newsletter Double-Opt-In | Standard | ☐ |
| 7 | AVV abgeschlossen | Manuell | ☐ |
| 8 | Fonts lokal gehostet | Automatisch | ☐ |
| 9 | Deutsche Server | Hetzner DE | ☐ |
| 10 | Recht auf Löschung | Account-Löschung | ☐ |

## Schritt 1: Impressum erstellen

Jede gewerbliche Website in Deutschland braucht ein Impressum:

1. Gehe zu **Einstellungen > Inhalte > Legal**
2. Erstelle die Seite **Impressum**
3. Pflichtangaben:
   - Vollständiger Name bzw. Firmenname
   - Anschrift (kein Postfach)
   - Kontaktdaten (E-Mail, Telefon)
   - Handelsregisternummer (falls vorhanden)
   - Umsatzsteuer-ID (falls vorhanden)
   - Verantwortlicher nach Paragraph 18 MStV

:::tip[Tipp]
Nutze einen Impressum-Generator (z.B. von eRecht24), um sicherzugehen, dass alle Pflichtangaben enthalten sind.
:::

## Schritt 2: Datenschutzerklärung erstellen

Die Datenschutzerklärung muss beschreiben, welche Daten du sammelst und verarbeitest:

1. Gehe zu **Einstellungen > Inhalte > Legal**
2. Erstelle die Seite **Datenschutzerklärung**
3. Relevante Punkte für Nexus-Nutzer:
   - Hosting bei Hetzner (Deutschland)
   - Zahlungsabwicklung über Stripe
   - E-Mail-Versand über deinen SMTP-Provider
   - Analytics (falls aktiviert)
   - Newsletter (falls aktiviert, mit Double-Opt-In)
   - Kontaktformulare

## Schritt 3: AGB erstellen

Wenn du Produkte verkaufst, brauchst du AGB:

1. Gehe zu **Einstellungen > Inhalte > Legal**
2. Erstelle die Seite **AGB**
3. Wichtige Inhalte:
   - Vertragspartner und Geltungsbereich
   - Vertragsschluss (Bestellvorgang)
   - Preise und Zahlungsbedingungen
   - Lieferung/Bereitstellung digitaler Inhalte
   - Widerrufsrecht (14 Tage bei digitalen Produkten beachten)
   - Haftung und Gewährleistung

:::warning[Wichtig]
Lass deine AGB von einem Anwalt prüfen oder nutze einen spezialisierten Generator (z.B. IT-Recht-Kanzlei, Händlerbund). Fehlerhafte AGB sind ein häufiger Abmahngrund.
:::

## Schritt 4: Cookie Consent aktivieren

1. Gehe zu **Einstellungen > System > Cookie Consent**
2. Aktiviere den Cookie-Banner
3. Wähle den **Opt-In Modus** (empfohlen):
   - Besucher müssen aktiv zustimmen
   - Erst nach Zustimmung werden Cookies gesetzt
   - Technisch notwendige Cookies sind ausgenommen
4. Passe den Text des Cookie-Banners an

## Schritt 5: Analytics datenschutzkonform nutzen

Nexus bietet integriertes Analytics:

- **IP-Anonymisierung** ist standardmäßig aktiv - IP-Adressen werden nicht vollständig gespeichert
- Keine externen Tracking-Dienste nötig (kein Google Analytics)
- Daten werden auf deutschen Servern gespeichert
- Erwähne Nexus Analytics in deiner Datenschutzerklärung

## Schritt 6: Newsletter mit Double-Opt-In

Wenn du das Newsletter Plugin nutzt:

1. Double-Opt-In ist in Nexus standardmäßig aktiv und kann nicht deaktiviert werden
2. Jeder Subscriber erhält eine Bestätigungs-E-Mail
3. Erst nach Klick auf den Bestätigungslink wird der Subscriber aktiv
4. Abmelde-Link ist automatisch in jeder Newsletter-E-Mail enthalten

Das ist gesetzlich vorgeschrieben und Nexus setzt es automatisch um.

## Schritt 7: AVV abschließen

Ein Auftragsverarbeitungsvertrag (AVV) ist nötig mit jedem Dienstleister, der personenbezogene Daten in deinem Auftrag verarbeitet:

- **Nexus/Start & Connect:** AVV anfordern per E-Mail
- **Stripe:** AVV in den Stripe-Einstellungen akzeptieren
- **SMTP-Provider:** AVV beim jeweiligen Anbieter abschließen (z.B. Mailgun)
- **Weitere Tools:** Für jedes Tool, das Kundendaten verarbeitet

:::info[Hinweis]
Führe eine Liste aller Auftragsverarbeiter. Diese Liste gehört als Anlage zur Datenschutzerklärung.
:::

## Schritt 8: Fonts werden lokal gehostet

Google Fonts direkt von Google-Servern zu laden, ist seit dem BGH-Urteil problematisch:

- Nexus hostet alle Google Fonts **automatisch lokal** auf deinem Server
- Es werden keine Verbindungen zu Google-Servern hergestellt
- Du musst nichts konfigurieren, das passiert automatisch
- Diesen Punkt kannst du direkt als erledigt markieren

## Schritt 9: Deutsche Server bei Hetzner

Deine Nexus-Instanz läuft auf deutschen Servern:

- Rechenzentrum: Hetzner, Deutschland
- Keine Datenübertragung in die USA oder andere Drittländer
- Serverstandort in der EU (DSGVO-konform)
- Diesen Punkt kannst du direkt als erledigt markieren

## Schritt 10: Recht auf Löschung umsetzen

Kunden haben das Recht, die Löschung ihrer Daten zu verlangen:

1. Kunden können ihren Account im Kundenportal selbst löschen
2. Alternativ: Gehe zu **Kunden**, suche den Kunden und wähle **Löschen**
3. Alle personenbezogenen Daten werden entfernt
4. Rechnungen bleiben aus steuerrechtlichen Gründen erhalten (Aufbewahrungspflicht)

## Zusammenfassung

Nexus nimmt dir viel DSGVO-Arbeit ab:
- Deutsche Server, lokale Fonts, IP-Anonymisierung und Double-Opt-In sind automatisch aktiv
- Du musst dich vor allem um Legal-Seiten, Cookie Consent und AVVs kümmern
- Nutze Generatoren oder einen Anwalt für rechtssichere Texte
- Prüfe regelmäßig, ob deine Angaben noch aktuell sind
