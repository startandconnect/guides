---
title: SEO-Einstellungen
order: 2
excerpt: Meta-Tags, Open Graph und Sitemap pro Seite konfigurieren
---

# SEO-Einstellungen

Für jede Seite kannst du SEO-Meta-Tags setzen. Diese werden im Split-Modus automatisch in den `<head>` eingefügt.

## Meta-Tags

Unter **Seite bearbeiten > SEO**:

- **Meta-Titel** — Titel in Google-Suchergebnissen und Browser-Tab (max. 60 Zeichen)
- **Meta-Beschreibung** — Kurzer Beschreibungstext in Suchergebnissen (max. 160 Zeichen)
- **Canonical URL** — Optional: wenn die Seite als Kopie einer anderen gelten soll
- **NoIndex** — Seite aus Suchmaschinen ausschließen (z.B. Danke-Seiten)

## Open Graph (Social Media)

Wenn deine Seite auf Facebook, LinkedIn oder Twitter geteilt wird:

- **OG-Titel** — Titel im Share-Preview
- **OG-Beschreibung** — Beschreibung im Share-Preview
- **OG-Bild** — Vorschaubild (empfohlen: 1200x630px aus der [Media Library](/spotlight/guide/features/media-library))

## Sitemap

Spotlight generiert automatisch eine `sitemap.xml` unter `deine-domain.com/sitemap.xml`, die alle veröffentlichten Seiten enthält. Du musst nichts tun — Google crawlt sie automatisch wenn du die Domain in der Google Search Console verbindest.

## Robots.txt

Unter **Einstellungen > SEO** kannst du eine eigene `robots.txt` hinterlegen, falls du Crawler steuern willst. Standardmäßig erlaubt Spotlight alle Bots.

## Strukturierte Daten

Wenn du JSON-LD Structured Data brauchst (z.B. für Rich Snippets), fügst du die einfach in deinen HTML-Code ein:

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Organization",
  "name": "Meine Firma",
  "url": "https://meine-website.de"
}
</script>
```
