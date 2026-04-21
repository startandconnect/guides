---
title: Portal
order: 5
excerpt: Der oeffentliche Kunden-Bereich
---

# Portal

Das offene Kunden-Interface deiner Nexus-Instance. Was Besucher deiner Domain sehen: Homepage, Shop, Blog, Produkt-Landingpages, Checkout, Kundenportal nach Login.

## Abgrenzung zum Admin-Bereich

- **Portal** - offen, von allen zugaenglich (meist mit Auth-Option)
- **Manage / Admin** - nur fuer eingeloggte Team-Mitglieder (`/manage`)
- **Customer Portal** - nur fuer eingeloggte Kunden (`/customer`)

## Was Portal enthaelt

- **Homepage** (`/`)
- **CMS-Pages** (`/about`, `/kontakt`, custom slugs)
- **Blog** (`/blog`, `/blog/:slug`)
- **Produkt-Lander** (`/p/:slug`)
- **Guide-Plugin-Seiten** (falls aktiv, z.B. `/glossar`)
- **Forms-Plugin-Seiten** (`/forms/:slug`)
- **Checkout** (`/checkout/:slug`)
- **Legal** (`/impressum`, `/datenschutz`, `/agb`)

## Design-Kontrolle

Du hast drei Stufen der Design-Kontrolle:

1. **Theme** - Farben, Font, Layout ueber Theme-Editor
2. **Page-Builder** - strukturierte Sections pro Page (Hero, Pricing, Testimonials, FAQ)
3. **HTML-Override** - komplett eigener HTML-Code fuer maximale Freiheit

## Smart Navigation

Auf startandconnect.com: individueller Header + Footer ueber [HTML-Override](/glossar/nexus-plattform/html-override). Zeigt je nach User-Status (Visitor / Customer / Team) unterschiedliche Navigation.

## Performance

Portal-Seiten sind ISR-cached (Next.js Incremental Static Regeneration). Cloudflare cacht anonyme Marketing-Routes zusaetzlich am Edge.

Typische TTFB fuer Cold-Load: 0.8-1.5s. Warm (CF HIT): 0.3-0.5s.

## SEO

Portal-Seiten generieren automatisch:
- Meta-Title + Description (pro Page konfigurierbar)
- Open-Graph-Tags (Social-Sharing)
- JSON-LD-Structured-Data (Organization, Product, BlogPosting)
- XML-Sitemap unter `/sitemap.xml`
- `robots.txt`

## Anpassbarkeit

Jede Portal-Seite kann per HTML-Override oder Page-Builder-Sections komplett umgestaltet werden. Das Portal ist nicht "ein Template" - es ist dein Whitelabel-Storefront.
