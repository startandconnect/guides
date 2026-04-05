---
title: Portal & Branding
order: 3
excerpt: Grundeinstellungen, Farben, Fonts und Cookie Consent konfigurieren
---

# Portal & Branding

Unter **Einstellungen > Portal** konfigurierst du die grundlegenden Eigenschaften deiner Plattform.

## Grundeinstellungen

- **Portal-Name** - Der Name deiner Plattform (wird überall angezeigt)
- **Beschreibung** - Kurze Beschreibung für SEO und Metadaten
- **Logo** - Wird im Header, in E-Mails und im Login angezeigt
- **Währung** - Standard-Währung für Preise (z.B. EUR, CHF)
- **Zeitzone** - Für korrekte Zeitanzeigen und Cron Jobs
- **Sprache** - Standardsprache der Plattform
- **Support-E-Mail** - Wird in System-E-Mails und im Footer angezeigt

## Branding

Passe das Erscheinungsbild deiner Plattform an:

### Farben

- **Primärfarbe** - Hauptfarbe für Buttons, Links und Akzente
- **Sekundärfarbe** - Ergänzende Farbe für sekundäre Elemente
- **Akzentfarbe** - Für Highlights und Hover-Effekte
- **Dark Mode** - Aktivieren/deaktivieren, automatische Farbanpassung

### Favicon

Lade ein Favicon hoch (empfohlen: 32x32 PNG oder SVG). Wird im Browser-Tab angezeigt.

### Font-Auswahl

Wähle aus einer Liste verfügbarer Google Fonts. Alle Fonts werden lokal gehostet - keine Requests an Google-Server.

:::info[Hinweis]
Fonts werden DSGVO-konform lokal ausgeliefert. Es werden keine Verbindungen zu externen Servern hergestellt.
:::

## Analytics

- **Tracking aktivieren** - Seitenaufrufe und Events erfassen
- **Tracking deaktivieren** - Keine Datenerhebung (z.B. für interne Portale)

Analytics-Daten sind nur im Admin-Bereich unter **Analytics** sichtbar.

## Cookie Consent

Nexus bietet drei Modi für den Cookie-Banner:

| Modus | Beschreibung | Empfohlen für |
|---|---|---|
| **Opt-In** | Nutzer muss aktiv zustimmen, bevor Cookies gesetzt werden | EU/DACH (DSGVO) |
| **Opt-Out** | Cookies werden gesetzt, Nutzer kann ablehnen | Nicht-EU |
| **Cookieless** | Kein Banner, keine Tracking-Cookies | Interne Portale |

:::tip[Tipp]
Für Portale mit Nutzern aus der EU ist **Opt-In** die rechtssichere Wahl. Tracking startet erst nach Zustimmung.
:::

Der Cookie-Banner passt sich automatisch an dein Branding an und ist auf allen Seiten sichtbar, bis der Nutzer eine Wahl getroffen hat.
