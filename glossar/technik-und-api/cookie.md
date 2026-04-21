---
title: Cookie
order: 10
excerpt: Kleine Daten die der Browser pro Website speichert
---

# Cookie

Kleiner Datensatz, den der Browser pro Website speichert und bei jedem Request automatisch mitschickt. Bekannt aus dem Cookie-Banner.

## Was Cookies gut koennen

- **Sessions halten** - "eingeloggt bleiben" nach Browser-Schliessen
- **Preferences** - Sprache, Theme, Layout merken
- **Shopping-Cart** - Artikel-Inhalt zwischen Seiten behalten
- **Tracking** - was der Nutzer auf der Seite tut (problematisch, siehe DSGVO)

## Attribute

Ein Cookie hat mehr als Key-Value. Entscheidend:

- **HttpOnly** - JavaScript kann das Cookie NICHT lesen. Schutz vor XSS.
- **Secure** - nur ueber HTTPS uebertragen
- **SameSite** - wird das Cookie bei Cross-Site-Requests mitgeschickt? Optionen: Strict, Lax, None
- **Expires/Max-Age** - wann laeuft's ab
- **Path** - auf welchen URL-Pfaden aktiv
- **Domain** - welche (Sub-)Domain

## Nexus-Cookies

- `auth-token` - eingeloggte Session (HttpOnly, Secure, SameSite=Lax, 30 Tage)
- `locale` - Sprachpraeferenz (1 Jahr)
- `cookieConsent` - Cookie-Banner-Entscheidung (1 Jahr)
- Optional `_ga` (Google Analytics) nur wenn User zugestimmt hat

## First-Party vs Third-Party

- **First-Party** - von der Website gesetzt die du gerade besuchst
- **Third-Party** - von einer anderen Domain (z.B. Facebook-Pixel auf einer fremden Seite)

Third-Party-Cookies werden 2026 von allen Browsern blockiert. Fuer Tracking-Zwecke werden sie durch First-Party-Alternativen ersetzt (z.B. Server-Side-Tracking).

## Cookie-Banner

DSGVO-Pflicht fuer nicht-essentielle Cookies. Nexus hat Banner eingebaut. Essentielle Cookies (Session, Praeferenzen) brauchen keine Zustimmung. Analytics, Marketing, Ads schon.

## Alternativen

- **localStorage** - nur Client-seitig, nicht automatisch im Request
- **sessionStorage** - wie localStorage aber verschwindet beim Tab-Schliessen
- **IndexedDB** - grosse Datenmengen

Cookies werden nur gebraucht wenn Daten AUTOMATISCH zum Server muessen.
