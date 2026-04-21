---
title: DNS
order: 13
excerpt: Wie Domains zu IP-Adressen werden
---

# DNS (Domain Name System)

Das Telefonbuch des Internets. Uebersetzt lesbare Domains (`startandconnect.com`) in IP-Adressen (`91.98.132.56`). Ohne DNS muesstest du IPs auswendig lernen.

## Wie funktioniert das

Du tippst `startandconnect.com` in den Browser. Passiert:

1. Browser fragt seinen DNS-Server: "Was ist die IP?"
2. DNS-Server geht durch die Hierarchie: `.com` → `startandconnect` → IP
3. Browser bekommt `91.98.132.56`
4. Browser baut Verbindung zu dieser IP auf

## Wichtige DNS-Record-Typen

- **A** - IPv4-Adresse (`1.2.3.4`)
- **AAAA** - IPv6-Adresse
- **CNAME** - Alias auf andere Domain (`shop.example.com` → `nexus.example.com`)
- **MX** - Mail-Server (`mail.google.com`)
- **TXT** - beliebiger Text (SPF, DKIM, Domain-Verifikation)
- **NS** - Name-Server fuer diese Domain

## TTL (Time To Live)

Wie lange ein DNS-Eintrag gecached werden darf. Kleinere TTL = Aenderungen schneller sichtbar, aber mehr DNS-Queries. Typisch 300-3600 Sekunden.

## Eigene Domain mit Nexus verbinden

1. **CNAME** von deiner Domain auf Nexus-URL (z.B. `shop.beispiel.de` CNAME `beispiel-shop.nexus.sac.run`)
2. DNS-Propagation abwarten (meist wenige Minuten, max 48h)
3. Nexus erstellt automatisch SSL-Zertifikat via Let's Encrypt

## Cloudflare als DNS-Provider

SAC nutzt Cloudflare fuer `startandconnect.com` und `sac.run`. Vorteile:
- Schnelle DNS-Aufloesung weltweit
- Kostenloser DDoS-Schutz
- CDN-Caching integriert
- Einfaches UI fuer Records

## Troubleshooting

- `dig deinedomain.de` - zeigt was der DNS antwortet
- `nslookup deinedomain.de` - aelterer aber universeller Befehl
- whatsmydns.net - zeigt Propagation-Status weltweit
- Browser-DNS-Cache oft die Ursache fuer "klappt bei mir nicht aber bei anderen"
