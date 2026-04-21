---
title: JWT
order: 6
excerpt: Auth-Tokens die Informationen enthalten
---

# JWT (JSON Web Token)

Kompakter Token, der Nutzer-Information kryptografisch signiert enthaelt. Nexus nutzt JWT fuer Session-Management im Admin und Customer-Portal.

## Aufbau

Ein JWT besteht aus drei Teilen, durch Punkte getrennt:

```
header.payload.signature
```

- **Header** - Metadaten (Algorithmus, Typ)
- **Payload** - die eigentlichen Daten (User-ID, Rolle, Ablaufdatum)
- **Signature** - kryptografische Signatur, kann nur mit Server-Secret erzeugt werden

Alle drei Teile sind Base64-kodiert, das sieht dann z.B. so aus:
```
eyJhbGc...OiJIUzI.eyJ1c2V...XJJZCI.XYZabc...
```

## Wofuer

Statt bei jedem Request in der Datenbank "ist dieser User eingeloggt und welche Rolle hat er?" nachzuschauen, steht das schon im JWT. Server-Performance-Vorteil.

## Warum das sicher ist

- Payload ist NICHT verschluesselt - jeder kann den Inhalt lesen (Base64 ist kein Krypto)
- Payload ist aber SIGNIERT - Aenderungen wuerden die Signatur invalidieren
- Server prueft bei jedem Request: Signatur gueltig? Token nicht abgelaufen? → OK

## Nexus JWT-Konfiguration

- **Admin-Token** Lifetime: 30 Tage
- **Refresh-Token** separates System, laenger gueltig
- Werden als `HttpOnly`-Cookies gesetzt (JavaScript kann sie nicht lesen - Schutz gegen XSS)

## Sicherheits-Pitfalls

- **Kein sensitives Datenhalten** - Payload ist lesbar, keine Passwoerter oder Geheimnisse rein
- **Revocation** - JWTs koennen nicht einzeln widerrufen werden (sie sind einfach gueltig bis Ablauf). Workaround: kurze Lifetime + Refresh
- **Algorithmen** - immer Asymmetrisch (RS256) oder symmetrisch mit starkem Secret (HS256). "none"-Algorithmus ist ein bekanntes Angriffs-Vector
