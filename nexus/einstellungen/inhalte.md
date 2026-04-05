---
title: Inhalte & SEO
order: 6
excerpt: Homepage, Legal-Seiten, SEO und Redirects verwalten
---

# Inhalte & SEO

Unter **Einstellungen > Inhalte** verwaltest du statische Seiten, rechtliche Texte und Suchmaschinenoptimierung.

## Homepage-Einstellungen

- **Titel** - Hauptüberschrift auf der Startseite
- **Beschreibung** - Untertitel oder Kurzbeschreibung
- **Featured Products** - Ausgewählte Produkte, die auf der Startseite hervorgehoben werden

## Legal

Konfiguriere die rechtlich erforderlichen Seiten deines Portals:

- **AGB** - Allgemeine Geschäftsbedingungen
- **Datenschutzerklärung** - Informationen zur Datenverarbeitung
- **Impressum** - Pflichtangaben nach TMG/DDG
- **Cookie Policy** - Informationen zu verwendeten Cookies
- **Widerrufsbelehrung** - Widerrufsrecht für Verbraucher

Für jede Seite kannst du entweder eine **URL** zu einer externen Seite hinterlegen oder den **Text direkt** in Nexus eingeben (Markdown-Editor).

:::warning[Wichtig]
Impressum und Datenschutzerklärung sind in Deutschland, Österreich und der Schweiz gesetzlich vorgeschrieben. Stelle sicher, dass diese Seiten korrekt befüllt sind.
:::

## SEO

### Standard Meta Tags

- **Meta Title** - Standard-Seitentitel (Fallback, wenn Seiten keinen eigenen haben)
- **Meta Description** - Standard-Beschreibung für Suchmaschinen
- **OG Image** - Standard-Bild für Social Media Shares

### Sitemap & robots.txt

- **Sitemap** - Wird automatisch unter `/sitemap.xml` generiert
- **robots.txt** - Wird automatisch generiert, kann manuell überschrieben werden

### Structured Data

Nexus generiert automatisch JSON-LD Structured Data für Produkte, Organisation und Breadcrumbs. Dies verbessert die Darstellung in Suchergebnissen.

## Redirects

Richte URL-Weiterleitungen ein:

- **301 (Permanent)** - Für dauerhaft verschobene Seiten (SEO-Wert wird übertragen)
- **302 (Temporär)** - Für vorübergehende Weiterleitungen

Pro Redirect gibst du **Quell-URL** und **Ziel-URL** an.

:::tip[Tipp]
Nutze 301-Redirects, wenn du Seiten umbenennst oder zusammenlegst, damit bestehende Links und SEO-Rankings erhalten bleiben.
:::

## Dashboard-Guide

Erstelle individuelle Onboarding-Schritte für neue Nutzer. Der Guide wird im Dashboard angezeigt und führt Nutzer durch die wichtigsten Funktionen:

- Schritte hinzufügen mit Titel, Beschreibung und Link
- Reihenfolge per Drag & Drop festlegen
- Nutzer können Schritte als erledigt markieren
