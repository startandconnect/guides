---
title: HTTPS und SSL
order: 14
excerpt: Verschluesselte Verbindungen zwischen Browser und Server
---

# HTTPS und SSL/TLS

HTTPS ist HTTP mit Verschluesselung. Das "S" steht fuer Secure. Ohne HTTPS koennte jeder im gleichen WLAN deine Passwoerter mitlesen.

## Wie das funktioniert

Beim Verbindungsaufbau:
1. Browser sagt: "Ich will mit dir reden"
2. Server zeigt sein SSL-Zertifikat - signiert von einer vertrauenswuerdigen CA (Certificate Authority)
3. Browser prueft: ist das Zertifikat gueltig, zur richtigen Domain, nicht abgelaufen, von vertrauten CA?
4. Wenn ja: beide tauschen Session-Schluessel aus, ab jetzt verschluesselt

## SSL vs TLS

- **SSL** ist der alte Begriff (Versions 1-3, alle deprecated)
- **TLS** ist der aktuelle Standard (1.2 und 1.3)
- Man sagt trotzdem "SSL-Zertifikat" weil historisch

## TLS-Versionen

- **TLS 1.0** - deprecated, unsicher
- **TLS 1.1** - deprecated
- **TLS 1.2** - aktueller Standard, breit unterstuetzt
- **TLS 1.3** - neueste Version, schneller (weniger Roundtrips), sicherer

Cloudflare bei SAC erzwingt mindestens TLS 1.2.

## Let's Encrypt

Kostenlose automatische Zertifikate. Ersetzt kommerzielle CAs (wo Zertifikate frueher 100-500 Euro pro Jahr kosteten).

- Zertifikat gueltig 90 Tage
- Automatische Verlaengerung 30 Tage vor Ablauf
- Validierung via DNS oder HTTP-Challenge

Nexus nutzt Let's Encrypt automatisch fuer alle Kunden-Domains.

## Haeufige Probleme

- **Zertifikat abgelaufen** - Browser warnt "nicht sicher". Sofort verlaengern.
- **Falsche Domain** - Zertifikat fuer `example.com` gilt NICHT fuer `www.example.com`. Beide einbeziehen.
- **Mixed Content** - HTTPS-Seite laedt HTTP-Resource (z.B. Bild). Browser blockiert oder warnt. Alles auf HTTPS umstellen.
- **Certificate Transparency Logs** - alle Zertifikate sind oeffentlich gelogged (Schutz gegen schurkische CAs)

## HSTS

HTTP Strict Transport Security. Header der sagt "dieser Server ist IMMER HTTPS, auch wenn ich HTTP tippe - direkt zu HTTPS umleiten". Schutz gegen Downgrade-Angriffe.

Nexus setzt HSTS mit `max-age=31536000` (1 Jahr) + `includeSubDomains`.
