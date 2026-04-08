---
title: Website & Seiten
order: 2
excerpt: Page Builder, HTML Override, SEO und eigene Domain
---

# Website & Seiten

Baue deine komplette Website in Nexus. Der Page Builder reicht für die meisten Seiten - für volle Kontrolle nutzt du den HTML Override mit der `window.nx` API. Alles auf deiner eigenen Domain mit SSL.

## Seiten erstellen

Unter **Seiten** verwaltest du alle Seiten deiner Website:

1. Klicke auf **Neue Seite**
2. Wähle Titel und Slug (URL-Pfad, z.B. `/über-uns`)
3. Füge Sections hinzu oder aktiviere den HTML Override

Jede Seite kann als Startseite festgelegt werden. Du kannst beliebig viele Seiten anlegen.

## Page Builder

Der Page Builder arbeitet mit Sections, die du per Drag & Drop anordnest:

| Section | Funktion |
|---------|----------|
| **Hero** | Großer Header mit Titel, Untertitel und CTA-Button |
| **Text** | Formatierter Textblock |
| **Image** | Einzelbild oder Bildergalerie |
| **Product-Grid** | Zeigt deine Produkte automatisch an, filterbar nach Kategorie |
| **Blog-Grid** | Listet aktuelle Blog-Artikel auf |
| **FAQ** | Akkordeon mit Fragen und Antworten |
| **Pricing** | Preistabelle mit Vergleichsfunktion |

Jede Section hat eigene Einstellungen für Layout, Farben, Abstände und Hintergründe. So baust du ohne Code professionelle Landingpages zusammen.

## HTML Override System v2

Wenn der Page Builder nicht reicht, aktivierst du den HTML Override:

1. Öffne die Seite > **Einstellungen**
2. Aktiviere **HTML Override**
3. Schreibe dein eigenes HTML, CSS und JavaScript

:::info[Hinweis]
Das HTML Override System v2 arbeitet mit **globalem Scope** - kein IIFE nötig. Dein Code wird direkt ausgeführt, Variablen und Funktionen sind global verfügbar.
:::

### window.nx API

Im HTML Override hast du Zugriff auf die `window.nx` API. Damit steuerst du Nexus-Features direkt aus deinem Code:

- **Produkte laden** - Produktdaten dynamisch abfragen
- **Checkout öffnen** - Checkout programmatisch starten
- **Theme auslesen** - Aktuelles Farbschema und Branding nutzen
- **Blog-Daten** - Blog-Artikel laden und darstellen

So baust du komplett eigene Designs, die trotzdem nahtlos mit dem Nexus-Backend arbeiten.

## SEO

Jede Seite hat eigene SEO-Einstellungen:

- **Meta Title** - Titel in Suchergebnissen (max. 60 Zeichen empfohlen)
- **Meta Description** - Beschreibung unter dem Titel (max. 155 Zeichen)
- **Canonical URL** - Vermeidet Duplicate Content bei mehreren URLs
- **noIndex** - Seite komplett von Suchmaschinen ausschließen

:::tip[Tipp]
Setze für jede wichtige Seite einen individuellen Meta Title und eine Description. Das verbessert deine Klickrate in den Suchergebnissen deutlich.
:::

## OG Image Generator v3

Nexus generiert automatisch Open-Graph-Bilder für Social Media Previews. Der OG Image Generator v3 ist pro Seite anpassbar - du bestimmst Titel, Beschreibung und Design. So sehen deine Links auf LinkedIn, X und Facebook professionell aus.

## Erfolgsseite nach dem Checkout

Nach einem erfolgreichen Kauf wird der Kunde automatisch auf die Erfolgsseite weitergeleitet.

- **Standard-Erfolgsseite** - Nexus zeigt automatisch eine Bestätigungsseite mit Bestellnummer und den nächsten Schritten an
- **Individuelle Erfolgsnachrichten** - pro Produkt konfigurierbar unter Produkt > After-Sales. So bekommt jeder Käufer eine passende Nachricht
- **HTML Override** - für volle Kontrolle schreibst du dein eigenes HTML. Aktiviere den Override in den Seiteneinstellungen der Erfolgsseite

### Verfügbare Variablen

In der Erfolgsnachricht und im HTML Override stehen dir diese Variablen zur Verfügung:

| Variable | Beschreibung |
|----------|-------------|
| `{{kundenname}}` | Vor- und Nachname des Kunden |
| `{{produktname}}` | Name des gekauften Produkts |
| `{{bestellnummer}}` | Eindeutige Bestellnummer |
| `{{betrag}}` | Bezahlter Betrag |
| `{{portal_url}}` | Link zum Kundenportal |

### Beispiel: Custom Erfolgsseite

```html
<div style="text-align: center; padding: 40px;">
  <h1>Vielen Dank, {{kundenname}}!</h1>
  <p>Deine Bestellung <strong>#{{bestellnummer}}</strong> war erfolgreich.</p>
  <p>Du hast <strong>{{produktname}}</strong> gekauft.</p>
  <a href="{{portal_url}}" style="
    display: inline-block;
    padding: 12px 24px;
    background: #2563eb;
    color: white;
    border-radius: 8px;
    text-decoration: none;
  ">Zum Kundenportal</a>
</div>
```

## Abbruchseite

Wenn der Kunde den Checkout abbricht, wird er auf die Abbruchseite weitergeleitet.

- **Standard-Abbruchseite** - Nexus zeigt eine einfache Seite mit der Möglichkeit, zurück zum Shop zu gehen
- **HTML Override** - du kannst die Seite komplett anpassen, um den Kunden zurückzugewinnen

:::tip[Tipp]
Nutze die Abbruchseite aktiv: Baue einen CTA-Button zurück zum Produkt ein, zeige nochmal die wichtigsten Vorteile oder biete einen Rabattcode an. So holst du abgebrochene Käufe zurück.
:::

## Eigene Domain und SSL

Unter **Einstellungen > Domain** verbindest du deine eigene Domain. SSL-Zertifikate werden automatisch erstellt und erneuert. Deine gesamte Website, der Checkout und das Kundenportal laufen auf deiner Domain.
