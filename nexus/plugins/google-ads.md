---
title: Google Ads
order: 12
excerpt: DSGVO-konformes Server-Side Conversion Tracking und Closed-Loop Reporting
---

# Google Ads

Verfolge den gesamten Weg vom Klick auf deine Google Ads Anzeige bis zum Kauf - DSGVO-konform und ohne Tag Manager. Nexus meldet Conversions serverseitig an Google Ads zurück und zeigt dir den echten ROI deiner Kampagnen.

## OAuth2 Setup

Die Verbindung zu Google Ads läuft über OAuth2:

1. Gehe zu **Einstellungen > Plugins > Google Ads**
2. Trage deine Google Cloud Credentials ein:
   - **Client ID** - Aus der Google Cloud Console
   - **Client Secret** - Aus der Google Cloud Console
   - **Redirect URI** - Wird von Nexus vorgegeben
3. Klicke auf **Verbinden** und autorisiere den Zugriff
4. Nexus erhält einen Token und die Verbindung steht

:::warning[Wichtig]
Die Google Cloud Credentials erstellst du in der Google Cloud Console unter APIs & Services > Credentials. Aktiviere dort die Google Ads API.
:::

## GCLID-Tracking

GCLID (Google Click Identifier) ist der Schlüssel zum Conversion Tracking:

- Nexus erfasst den GCLID automatisch aus URL-Parametern wenn ein Besucher über eine Google Ads Anzeige kommt
- Die Erfassung erfolgt **serverseitig** - kein Tag Manager, kein JavaScript, kein Cookie-Banner nötig
- Der GCLID wird dem Kontakt zugeordnet und bei einem späteren Kauf für das Conversion Tracking verwendet

## Server-Side Conversion Tracking

Wenn ein Kunde kauft, meldet Nexus die Conversion serverseitig an Google Ads:

1. Kunde klickt auf eine Google Ads Anzeige (GCLID wird erfasst)
2. Kunde kauft ein Produkt in Nexus
3. Nexus sendet die Conversion mit dem **echten Umsatz** an Google Ads
4. Google Ads kann die Kampagne auf echte Verkäufe optimieren

Das ist deutlich genauer als pixelbasiertes Tracking und funktioniert auch bei Ad-Blockern.

### Conversion Actions

Konfiguriere unter den Plugin-Einstellungen welche Aktionen als Conversion gemeldet werden:

- Kauf abgeschlossen
- Umsatzhöhe pro Transaktion

Jede Conversion Action wird mit dem korrekten Betrag an Google Ads gemeldet.

## Performance Dashboard

Das Dashboard unter **Google Ads** zeigt dir die wichtigsten Metriken:

- **Kampagnen-Übersicht** - Alle aktiven Kampagnen mit Klicks, Impressionen und Kosten
- **Cost per Lead (CPL)** - Was dich ein Lead über Google Ads kostet
- **Cost per Acquisition (CPA)** - Was dich ein zahlender Kunde kostet
- **ROI** - Return on Investment: Umsatz im Verhältnis zu den Werbekosten

## Closed-Loop Reporting

Der große Vorteil gegenüber Standard-Tracking: Nexus kennt den echten Kundenumsatz.

- **Werbekosten vs. echter Umsatz** - Vergleiche was du für Ads ausgibst mit dem tatsächlich generierten Umsatz
- **Customer Attribution** - Sieh genau welche Kampagne welchen Kunden gebracht hat
- **Langfristige Analyse** - Verfolge den Customer Lifetime Value pro Kampagne

:::tip[Tipp]
Nutze die Customer Attribution um zu verstehen welche Kampagnen wirklich profitabel sind - nicht nur die mit den meisten Klicks, sondern die mit dem höchsten Kundenwert.
:::

## Conversion Log

Unter **Google Ads > Conversions** findest du das detaillierte Log:

- Jede gemeldete Conversion mit Zeitstempel und Betrag
- Der zugehörige GCLID und die Kampagne
- **Status** - Ob die Conversion erfolgreich an Google Ads gemeldet wurde
- **API-Response** - Die Antwort von Google Ads für die Fehleranalyse

Das Log hilft bei der Fehlersuche wenn Conversions nicht korrekt zugeordnet werden.
