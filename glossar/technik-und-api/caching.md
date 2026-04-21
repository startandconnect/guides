---
title: Caching
order: 16
excerpt: Daten temporaer vorhalten statt neu berechnen
---

# Caching

Daten die einmal berechnet oder geladen wurden, werden fuer spaetere Anfragen zwischengespeichert. Spart Zeit, Bandbreite, CPU, Kosten.

## Wo ueberall gecacht wird

- **Browser-Cache** - dein Chrome behaelt Bilder und CSS lokal
- **CDN-Cache** - Cloudflare-Edge haelt haeufig angefragte Seiten
- **Reverse-Proxy-Cache** - Traefik / Nginx vor der App
- **Application-Cache** - Redis, in-memory in der App
- **Database-Cache** - Postgres cached selber, zusaetzlich Query-Cache

Gute Apps stapeln diese Ebenen.

## Cache-Strategien

**Network First** - erst Netzwerk fragen, bei Fehler Cache. Immer aktuell, bei langsamem Netz langsam.

**Cache First** - erst Cache, dann Netzwerk. Instant, aber evtl. veraltet.

**Stale-While-Revalidate** - Cache sofort zurueckgeben, parallel im Hintergrund aktualisieren. Best of both worlds.

**Network Only** - nie cachen (fuer dynamische API-Calls)

## TTL (Time To Live)

Wie lange ein Cache-Eintrag gueltig ist. Zu kurz = viele Cache-Misses. Zu lang = veraltete Daten.

Faustregeln:
- **Static Assets** (Bilder, Fonts) - 1 Jahr, mit Versioning
- **CSS/JS-Bundles** - 1 Jahr, mit Hash im Namen
- **HTML-Pages** - 1-5 Minuten (Edge), 60 Sekunden (ISR)
- **API-Responses** - meistens nicht cachen, einzelne Settings ggf 5-10 Min
- **User-Session-Daten** - nie cachen

## Cache-Invalidation

"There are two hard things in CS: cache invalidation and naming things." - Phil Karlton.

Wenn du Daten aenderst, musst du entscheiden: welche Caches muessen weg?

- **Time-basiert** - warten bis TTL abgelaeuft. Einfach, manchmal zu langsam.
- **Event-basiert** - bei Update explizit invalidieren
- **Version-basiert** - neue URL fuer neue Version, alter Cache verfaellt

## Nexus-Caching

- **Redis** fuer Settings-Cache (verteilter in-memory-Cache)
- **Next.js ISR** fuer statische Pages (60s revalidate)
- **React Query** Client-seitig (Stale-While-Revalidate)
- **Cloudflare Edge** fuer Marketing-Pages (edge_ttl 300s)
- **Browser-Cache** fuer Assets (1 Jahr mit Hash-Versioning)

Alle Ebenen zusammen: Homepage laedt typisch in 300-900ms.
