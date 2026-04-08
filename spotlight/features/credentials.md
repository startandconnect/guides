---
title: Credentials & API-Keys
order: 2
excerpt: API-Keys sicher ablegen und in Frontend-Code nutzen
---

# Credentials & API-Keys

Wenn deine Website externe Dienste nutzt (OpenAI, Brevo, Google Maps, Airtable) brauchst du API-Keys. Die dürfen NIE direkt ins Frontend - sonst kann sie jeder in den DevTools auslesen. Spotlight löst das mit dem Credential-System.

## So funktioniert's

1. Du legst einen Credential im Admin an (`Einstellungen > Credentials`)
2. Spotlight stellt unter `/api/proxy/<name>` einen Proxy-Endpoint bereit
3. Du rufst den Proxy von deinem JavaScript auf - Spotlight fügt den API-Key serverseitig hinzu

Der Key ist damit nur auf dem Server sichtbar, nie im Browser.

## Credential anlegen

1. Gehe zu **Einstellungen > Credentials**
2. **Neuer Credential**
3. Eintragen:
   - **Name** - z.B. `brevo`, `openai`, `airtable`
   - **Service** - Wähle aus der Liste (oder `Custom` für eigene Dienste)
   - **API-Key** - Dein Key vom Dienst
   - **Base URL** - API-Endpoint (z.B. `https://api.brevo.com/v3`)
   - **Header-Name** - z.B. `api-key` oder `Authorization`
   - **Header-Prefix** - z.B. `Bearer ` (leer lassen wenn nicht nötig)
4. **Speichern**

## Im JavaScript nutzen

Aus deinem HTML-Override oder deiner Page:

```js
// POST an Brevo zum Newsletter anmelden
const res = await fetch('/api/proxy/brevo/contacts', {
  method: 'POST',
  headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify({
    email: 'user@example.com',
    listIds: [2]
  })
});
const data = await res.json();
```

Spotlight routet den Call intern an `https://api.brevo.com/v3/contacts` und fügt den `api-key` Header hinzu.

## Welche Endpoints erlaubt sind

Du kannst pro Credential eine **Allowlist** von erlaubten Pfaden setzen. Default: alles erlaubt.

Beispiel Allowlist für Brevo:
```
POST /contacts
GET /account
```

Damit blockierst du ungewollte Aufrufe (z.B. kein Löschen, kein Auslesen aller Kontakte).

## Rate Limiting

Jeder Proxy-Endpoint hat ein Rate Limit:

- **60 Requests / Minute** pro IP
- **1.000 Requests / Tag** pro Credential

Das schützt dich vor Missbrauch durch Bots.

## Beispiele

### OpenAI (ChatGPT-API)

```js
const res = await fetch('/api/proxy/openai/chat/completions', {
  method: 'POST',
  headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify({
    model: 'gpt-4o-mini',
    messages: [{ role: 'user', content: userInput }]
  })
});
```

### Airtable

```js
const res = await fetch('/api/proxy/airtable/MyBase/Leads', {
  method: 'POST',
  headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify({
    records: [{ fields: { Email: email, Name: name } }]
  })
});
```

### Google Maps (Geocoding)

Für Geocoding brauchst du keinen Browser-Key mehr - der Server-Proxy übernimmt es:

```js
const res = await fetch(
  `/api/proxy/google-maps/maps/api/geocode/json?address=${encodeURIComponent(address)}`
);
```
