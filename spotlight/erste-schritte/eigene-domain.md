---
title: Eigene Domain verbinden
order: 3
excerpt: Deine Domain auf Spotlight zeigen lassen - DNS und SSL
---

# Eigene Domain verbinden

Deine Spotlight-Instanz läuft standardmäßig unter `dein-slug.s2.sac.run`. Für den produktiven Einsatz willst du aber deine eigene Domain.

## 1. Domain im Admin hinterlegen

1. Gehe zu **Einstellungen > Domain**
2. Gib deine Domain ein — z.B. `meine-website.de`
3. Klick auf **Speichern**

Spotlight zeigt dir jetzt die benötigten DNS-Einträge.

## 2. DNS-Einträge setzen

Bei deinem Domain-Provider (z.B. IONOS, Strato, Cloudflare) trägst du ein:

| Typ | Name | Wert |
|-----|------|------|
| A | @ | Wird im Admin angezeigt |
| A | www | Wird im Admin angezeigt |

Wenn du Cloudflare nutzt, setze den Proxy-Modus erstmal auf **DNS only** (graue Wolke), bis das SSL-Zertifikat erstellt wurde.

## 3. Warten & Verifizieren

DNS-Änderungen brauchen 5 Minuten bis 24 Stunden. Nach ein paar Minuten kannst du im Admin auf **DNS prüfen** klicken. Sobald der Check grün ist, wird automatisch ein SSL-Zertifikat via Let's Encrypt erstellt.

## 4. SSL aktiv

Sobald der SSL-Status auf `✓ Aktiv` steht, ist deine Website unter `https://meine-website.de` erreichbar. Fertig.

## www oder ohne www?

Du kannst in den Einstellungen festlegen, ob:

- **`www.meine-website.de`** → `meine-website.de` weiterleiten (empfohlen)
- **oder umgekehrt**

Beide Varianten funktionieren mit SSL.

## Häufige Probleme

**DNS-Check schlägt fehl** — Warte 10-30 Minuten, teste dann nochmal. Manche Provider brauchen länger.

**SSL-Zertifikat wird nicht erstellt** — Stell sicher dass DNS bereits funktioniert und Cloudflare auf `DNS only` steht (nicht `Proxied`).

**Website zeigt "404" nach Domain-Setup** — Die Default-Page muss gesetzt sein. Gehe zu **Seiten**, öffne deine Startseite und markier sie als `Default Page`.
