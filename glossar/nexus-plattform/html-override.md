---
title: HTML Override
order: 14
excerpt: Eigenes HTML/CSS/JS in Nexus-Seiten einbauen
---

# HTML Override

Feature mit dem du eigenen HTML/CSS/JS-Inhalt in Nexus-Seiten einfuegst. Fuer komplette Design-Freiheit ohne die Plattform verlassen zu muessen.

## Wo moeglich

- **Homepage** - komplette Startseite selber bauen
- **CMS-Pages** - jede `/slug`-Seite
- **Blog-Artikel** - Content-Ebene
- **Produkt-Lander** (`/p/:slug`)
- **Header** (Nav-HTML-Override)
- **Footer** (Nav-HTML-Override)

## Wie es aussieht

Du kriegst einen Editor mit drei Tabs:
- **HTML** - der Body-Content
- **CSS** - eigene Styles (scoped auf die Page)
- **JavaScript** - Interaktivitaet

Was du schreibst wird direkt in die Seite eingefuegt - mit Zugang zu ein paar Nexus-spezifischen Variablen und APIs.

## Nexus-spezifische Features im Override

- **`{{variablen}}`** fuer dynamische Werte (Portal-Name, Brand-Color, User-Infos)
- **`window.nx` JavaScript-API** mit `nx.theme.toggle()`, `nx.checkout.open(productId)`, `nx.products.formatPrice()`
- **Form-Shortcodes** `[form:slug]` rendern eingebettete Forms
- **Product-Cards** mit Daten aus der DB

## User-Status-Varianten

Nav-HTML-Override hat drei Varianten:
- `visitor` - nicht eingeloggte Besucher
- `customer` - eingeloggte Kunden
- `team` - eingeloggte Admins

Je nach Status wird die passende Variante gerendert. Ermoeglicht z.B. Login-Button vs Dashboard-Link im Header.

## Google-Fonts-Proxy

Wenn du Google Fonts in deinem Override nutzt, werden sie automatisch lokal proxied. DSGVO-konform, kein Laden von Google-Servern direkt.

## SAC-Beispiel: Smart Navigation

startandconnect.com nutzt einen eigenen HTML-Override fuer Header + Footer (genannt "Smart Navigation"). Komplett eigener Code, eigenes Design, eigene Animationen.

## Limitierungen

- Nur Portal-Seiten, keine Admin-Overrides
- Scripts werden in isoliertem Scope gerendert - kein Zugriff auf React-Komponenten von Nexus selbst
- Cross-Site-Scripting wird durch Content-Security-Policy eingeschraenkt

## Wann NICHT nutzen

HTML-Override ist maechtig aber auch verantwortungsvoll. Wenn du Standard-Shop-UI willst: Page-Builder-Sections reichen. Override ist fuer custom Design-Visionen oder spezielle Landingpages.
