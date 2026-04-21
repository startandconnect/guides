---
title: REST
order: 2
excerpt: Das Standard-Muster fuer Web-APIs
---

# REST (Representational State Transfer)

Architektur-Stil fuer Web-APIs, der 2000 von Roy Fielding beschrieben wurde. REST-APIs sind der De-facto-Standard fuer moderne Systeme - inkl. Nexus.

## Kern-Prinzipien

- **Ressourcen** werden durch URLs adressiert (`/products`, `/orders/42`)
- **HTTP-Methoden** beschreiben was du tun willst (GET, POST, PATCH, DELETE)
- **Stateless** - jeder Request enthaelt alle Informationen, Server merkt sich nichts zwischen Requests
- **Einheitliches Interface** - gleiche Pattern fuer alle Endpoints

## HTTP-Methoden und ihre Bedeutung

| Methode | Zweck | Idempotent? |
|---|---|---|
| GET | Daten lesen | ja |
| POST | Neues anlegen | nein |
| PATCH | Teilweise aendern | meistens |
| PUT | Komplett ersetzen | ja |
| DELETE | Loeschen | ja |

## Typisches Beispiel

```
GET    /api/products         → alle Produkte
GET    /api/products/42      → Produkt mit ID 42
POST   /api/products         → Neues Produkt anlegen (Body: JSON)
PATCH  /api/products/42      → Produkt aendern (Body: nur geaenderte Felder)
DELETE /api/products/42      → Produkt loeschen
```

## Status-Codes

- **200** OK - alles gut
- **201** Created - neu angelegt
- **204** No Content - erfolgreich, keine Antwort (z.B. DELETE)
- **400** Bad Request - dein Request ist fehlerhaft
- **401** Unauthorized - nicht eingeloggt
- **403** Forbidden - keine Berechtigung
- **404** Not Found - Ressource existiert nicht
- **409** Conflict - Konflikt (z.B. Duplikat)
- **500** Server Error - wir haben gepatzt
- **503** Service Unavailable - wir sind gerade down

## REST vs GraphQL vs RPC

- **REST** - einfach, breit verstanden, viele Endpoints, manchmal overfetching
- **GraphQL** - eine Endpoint, Client bestimmt welche Felder. Flexibler, komplexer
- **gRPC / RPC** - binaere Protokolle, sehr schnell, weniger universell

Nexus ist klassisches REST. Fuer die allermeisten Faelle die beste Wahl.
