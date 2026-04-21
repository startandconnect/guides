---
title: API
order: 1
excerpt: Wie Programme miteinander reden
---

# API (Application Programming Interface)

Definierter Satz von Endpunkten ueber den ein Programm mit einem anderen redet. Wenn du in einer App auf "Zahlen mit PayPal" klickst, spricht die App ueber die PayPal-API mit PayPal.

## Was eine API ausmacht

- **Endpunkte** (URLs) mit definiertem Zweck: `/api/products` listet Produkte, `/api/orders` Bestellungen
- **Methoden** wie GET (lesen), POST (erstellen), PATCH (aendern), DELETE (loeschen)
- **Datenformat** - meistens JSON
- **Authentifizierung** - wer darf was, per API-Key oder Token

## Nexus-API

Ueber 1000 Endpoints, dokumentiert unter `https://deine-domain.de/api/docs` (Swagger UI). Jede Admin-Aktion in der UI ist auch per API moeglich.

**Beispiel:**
```bash
curl -H "x-api-key: deinkey" \
     https://deinshop.nexus/api/products
```

Liefert JSON mit allen Produkten.

## Warum APIs wichtig sind

- **Automation** - Scripts koennen wiederkehrende Aufgaben erledigen
- **Integration** - externe Tools (Zapier, Make) anbinden
- **KI-Steuerung** - Agents wie Claude Code koennen per API arbeiten
- **Eigene Interfaces** - bauen, die sich nicht vom Admin-UI abhaengig machen

## Public API vs Private API

- **Public API** - dokumentiert, fuer Kunden zum Integrieren, stabile Versionierung
- **Private API** - interne Endpoints des Produkts selbst, koennen sich aendern

Nexus publiziert seine komplette Core-API als Public.

## API-Versionierung

Wenn Endpoints sich unvereinbar aendern mussen: `/api/v1/...` → `/api/v2/...`. Alte Version bleibt eine Weile, Kunden koennen migrieren. Nexus hat noch kein v2, alles unter `/api`.
