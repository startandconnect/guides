---
title: API Einführung
order: 1
excerpt: REST-API für volle Kontrolle über deine Nexus-Instanz
---

# API Einführung

Nexus bietet eine umfassende REST-API mit über 900 dokumentierten Endpoints. Damit kannst du alles programmatisch steuern: Produkte, Bestellungen, Kunden, E-Mails und mehr.

## API-Dokumentation

Die interaktive API-Dokumentation findest du unter:

```
https://deine-domain.de/api/docs
```

Dort kannst du alle Endpoints sehen, ausprobieren und die Request/Response-Formate einsehen.

## API Key erstellen

1. Gehe zu **Einstellungen > Integrationen > API Keys**
2. Klicke auf **Neuer API Key**
3. Vergib einen Namen (z.B. "Meine App")
4. Wähle die Berechtigungen
5. Kopiere den Key - er wird nur einmal angezeigt

## Authentifizierung

Sende den API Key als Header mit jedem Request:

```bash
curl -H "x-api-key: nxs_dein_api_key" \
     -H "Content-Type: application/json" \
     https://deine-domain.de/api/products
```

## Berechtigungen

API Keys können auf bestimmte Bereiche eingeschränkt werden:

| Berechtigung | Beschreibung |
|-------------|-------------|
| `products:read` | Produkte lesen |
| `products:write` | Produkte erstellen und bearbeiten |
| `orders:read` | Bestellungen lesen |
| `customers:read` | Kunden lesen |
| `customers:write` | Kunden erstellen und bearbeiten |
| `settings:read` | Einstellungen lesen |
| `*` | Vollzugriff |

## Beispiele

### Produkte auflisten

```bash
curl -H "x-api-key: nxs_..." \
     https://deine-domain.de/api/products
```

### Bestellung abrufen

```bash
curl -H "x-api-key: nxs_..." \
     https://deine-domain.de/api/orders/ORDER_ID
```

### Kunden suchen

```bash
curl -H "x-api-key: nxs_..." \
     "https://deine-domain.de/api/customers?search=max@beispiel.de"
```

## Webhooks

Unter **Einstellungen > Integrationen > Webhooks** kannst du HTTP-Callbacks einrichten die bei bestimmten Events ausgelöst werden (z.B. neue Bestellung, neuer Kunde).

## Rate Limits

Die API hat keine harten Rate Limits, aber bitte halte dich an faire Nutzung. Bei übermäßig vielen Requests kann der Zugang temporär eingeschränkt werden.
