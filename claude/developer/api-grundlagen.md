---
title: API Grundlagen
order: 1
excerpt: Einstieg in die Anthropic API - Auth, erste Requests, wichtige Endpunkte
---

# API Grundlagen

Für Developer, die Claude in eigene Apps einbauen wollen.

## Auth

Anthropic API nutzt API Keys. Keys erstellst du im Anthropic Console.

TODO: Schritt für Schritt Key anlegen, sichere Ablage.

## Erster Request

```bash
curl https://api.anthropic.com/v1/messages \
  -H "x-api-key: $ANTHROPIC_API_KEY" \
  -H "anthropic-version: 2023-06-01" \
  -H "content-type: application/json" \
  -d '{
    "model": "claude-sonnet-4-6",
    "max_tokens": 1024,
    "messages": [{"role": "user", "content": "Hallo"}]
  }'
```

TODO: Request-Aufbau genau erklären, aktuelle Modell-IDs verifizieren.

## Wichtige Endpunkte

- `/v1/messages` - Hauptendpunkt für Chat
- `/v1/messages/count_tokens` - Tokens zählen vor dem Send
- Weitere: Files, Batches, Models

TODO: Komplette Liste mit kurzer Erklärung.

## Rate Limits

TODO: Aktuelle Limits, wie man sie erweitert, was bei 429 tun.

## Cost-Optimierung

- **Prompt Caching:** wiederkehrende Teile cachen und sparen
- **Batch API:** asynchrone Jobs für 50 Prozent Rabatt

TODO: Beide Features mit Beispiel.
