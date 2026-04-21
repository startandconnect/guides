---
title: CDN
order: 15
excerpt: Inhalte weltweit schnell ausliefern
---

# CDN (Content Delivery Network)

Netzwerk von Servern verteilt um die Welt, die statische Inhalte (Bilder, Videos, CSS, JS) naeher am Nutzer bereitstellen. Statt dass jeder User-Request zu deinem Origin-Server in Deutschland muss, wird er aus einem naheliegenden Edge-Server beantwortet.

## Wie das funktioniert

1. User aus Berlin besucht `startandconnect.com/nexus`
2. Browser holt HTML von Cloudflare-Edge in Frankfurt (15ms)
3. Browser holt Bilder / CSS / JS auch aus Frankfurt (nochmal 15ms)
4. Originserver in Nuernberg wird GAR NICHT belastet

Ohne CDN:
- Alles zum Origin-Server in Nuernberg (50-200ms je nach Standort)
- User in Sydney: 300-500ms Latenz

## CDN-Provider

- **Cloudflare** - Marktfuehrer, kostenlose Stufe, einfach zu setupen. SAC nutzt Cloudflare.
- **Fastly** - Enterprise-Fokus
- **AWS CloudFront** - wenn du eh AWS nutzt
- **Bunny CDN** - Low-Cost-Alternative
- **Akamai** - Enterprise-Urgestein

## Was gecacht wird

- **Bilder, Videos, Fonts** - meistens automatisch (statische Assets)
- **CSS, JS** - ja, mit Versionierung fuer Cache-Invalidation
- **HTML-Pages** - nur mit expliziter Regel (Cache-Rules bei CF)
- **API-Responses** - nein, dynamisch

## Cache-Invalidation

Wenn du ein Bild austauschst, wie bekommen die CDN-Edges das mit?

- **Query-String-Versionierung**: `/logo.png?v=2` → neue URL → cached als neue Ressource
- **Cache-Tag-Purge** (Pro-Feature): Files taggen, bei Update tag-basiert purgen
- **Purge Everything**: kompletter Cache-Wipe (brute force)

SAC-Cache-Management per `POST https://api.cloudflare.com/client/v4/zones/{zone}/purge_cache`.

## CDN als Firewall

Moderne CDNs sind nicht nur Caching, sondern auch:
- **DDoS-Protection** - absorbiert riesige Traffic-Spitzen
- **WAF** (Web Application Firewall) - blockiert boesartige Requests
- **Bot-Management** - zwischen echten Nutzern und Scrapern unterscheiden
- **Rate-Limiting** - per-IP oder Country

Cloudflare Free hat viel davon eingebaut.

## SAC-Setup

- `startandconnect.com` + `sac.run` hinter Cloudflare (Free Plan)
- Cache-Rules aktiv fuer anonymous Marketing-Routes (edge_ttl 300s)
- Argo Smart Routing nicht aktiviert (Pro-Feature, $20/mo)
