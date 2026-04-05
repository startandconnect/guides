---
title: Blog
order: 2
excerpt: Artikel schreiben, planen und mit SEO optimieren
---

# Blog

Betreibe einen vollwertigen Blog direkt in Nexus. Schreibe Artikel mit Rich Text, organisiere sie in Kategorien und Tags, optimiere für Suchmaschinen und erreiche deine Zielgruppe über RSS.

## Artikel erstellen

1. Gehe zu **Blog** im Seitenmenü
2. Klicke auf **Neuer Artikel**
3. Schreibe deinen Artikel im Rich Text Editor
4. Setze Kategorie, Tags und Featured Image
5. Konfiguriere die SEO-Einstellungen
6. Veröffentliche oder plane die Veröffentlichung

### Rich Text Editor

Der Editor unterstützt:

- **Text-Formatierung** - Überschriften (H1-H6), Fett, Kursiv, Unterstrichen, Durchgestrichen
- **Listen** - Nummeriert, unnummeriert, Checklisten
- **Medien** - Bilder hochladen oder per URL einbetten, Videos einbetten
- **Code-Blöcke** - Mit Syntax-Highlighting für verschiedene Sprachen
- **Einbettungen** - YouTube-Videos, Links mit Vorschau
- **Tabellen** - Strukturierte Daten direkt im Artikel

### Featured Image

Das Featured Image erscheint als Vorschaubild in der Blog-Übersicht und als OG-Image beim Teilen in sozialen Netzwerken. Lade ein eigenes Bild hoch oder nutze die automatische YouTube Thumbnail-Extraktion: Wenn dein Artikel ein YouTube-Video enthält, kann Nexus das Thumbnail automatisch als Vorschaubild verwenden.

## Kategorien & Tags

Organisiere deine Artikel auf zwei Ebenen:

- **Kategorien** - Hauptthemen wie "Marketing", "Produkt-Updates" oder "Tutorials". Jeder Artikel gehört zu einer Kategorie.
- **Tags** - Schlagwörter für feinere Zuordnung. Ein Artikel kann mehrere Tags haben.

Kategorien und Tags verwaltest du unter **Blog > Kategorien** bzw. **Blog > Tags**.

## SEO pro Artikel

Jeder Artikel hat eigene SEO-Felder:

- **Meta Title** - Der Titel der in Suchergebnissen erscheint
- **Meta Description** - Die Beschreibung unter dem Titel in Suchergebnissen
- **Slug** - Der URL-Pfad des Artikels (z.B. `/blog/mein-artikel`)
- **Focus Keyword** - Das Haupt-Keyword für die SEO-Analyse
- **Canonical URL** - Verhindert Duplicate Content bei Crossposting
- **noIndex** - Artikel von Suchmaschinen ausschließen

:::tip[Tipp]
Setze immer Meta Title und Description. Nexus zeigt dir eine Vorschau wie der Artikel in Google-Suchergebnissen aussehen wird.
:::

## Geplante Veröffentlichung

Du kannst Artikel für die Zukunft planen:

1. Setze den Status auf **Geplant**
2. Wähle Datum und Uhrzeit unter **publishedAt**
3. Der Artikel wird automatisch zum gewählten Zeitpunkt veröffentlicht

Geplante Artikel sind bis zur Veröffentlichung nur für Admins sichtbar.

## Blog-Übersicht

Die öffentliche Blog-Seite zeigt:

- **Featured Post** - Ein hervorgehobener Artikel ganz oben
- **Suchfeld** - Volltextsuche über alle Artikel
- **Kategorie-Filter** - Artikel nach Kategorie filtern
- **Artikelliste** - Alle veröffentlichten Artikel mit Vorschaubild, Titel und Excerpt

## Artikel-Ansicht

Jeder veröffentlichte Artikel bietet:

- **Table of Contents (TOC)** - Automatisch generiertes Inhaltsverzeichnis als Sidebar-Card. Beim Scrollen wird der aktuelle Abschnitt hervorgehoben (Scroll Spy).
- **Share Buttons** - Artikel teilen per Link kopieren, X/Twitter oder LinkedIn
- **Prev/Next Navigation** - Links zum vorherigen und nächsten Artikel

## RSS-Feed

Dein Blog hat automatisch einen RSS-Feed unter `/blog/rss.xml`. Deine Leser können ihn mit jedem RSS-Reader abonnieren.

## Blog-Einstellungen

Unter **Einstellungen > Plugins > Blog** konfigurierst du:

- **Titel** - Der Name deines Blogs
- **Beschreibung** - Kurzbeschreibung die im RSS-Feed und auf der Übersichtsseite erscheint
