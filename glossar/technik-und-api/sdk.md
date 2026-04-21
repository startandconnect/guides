---
title: SDK
order: 12
excerpt: Fertiges Tooling um eine API zu nutzen
---

# SDK (Software Development Kit)

Ein Paket aus Code, Dokumentation und Tools, mit dem Entwickler schneller eine Integration bauen koennen. Typisch: eine offizielle Client-Library die die rohe API abstrahiert.

## Beispiel

Ohne SDK mit roher Stripe-API:
```js
fetch('https://api.stripe.com/v1/charges', {
  method: 'POST',
  headers: {
    'Authorization': 'Bearer sk_test_...',
    'Content-Type': 'application/x-www-form-urlencoded'
  },
  body: new URLSearchParams({
    amount: '2000',
    currency: 'eur',
    source: 'tok_visa'
  })
})
```

Mit dem Stripe-SDK:
```js
await stripe.charges.create({
  amount: 2000,
  currency: 'eur',
  source: 'tok_visa'
});
```

Lesbarer, typ-sicher, mit IDE-Autocomplete.

## Was ein SDK typisch enthaelt

- **Client-Library** fuer mehrere Programmiersprachen (JavaScript, Python, Ruby, PHP, Go, ...)
- **Type-Definitionen** (TypeScript, Python-Stubs)
- **Beispiele** und Tutorials
- **CLI-Tools** fuer lokale Entwicklung
- **Test-Helpers** (Mocks, Fixtures)

## Braucht jedes Tool ein SDK

Nein. Kleine APIs kommen ohne aus - `fetch`, `requests`, `curl` reichen. SDK lohnt sich ab ~30-50 Endpoints oder wenn Authentifizierung kompliziert ist (z.B. Stripe-Signatur-Validierung).

## Nexus-SDK

Aktuell kein offizielles SDK. Nexus-API ist REST, nutzbar mit jedem HTTP-Client. Fuer Power-User: MCP-Server-Config liefert Claude-Code die komplette API als Tools. Ist praktisch das beste "SDK" fuer KI-Nutzung.

## Versionierung

Gute SDKs folgen SemVer (Semantic Versioning):
- Major.Minor.Patch (z.B. 2.14.3)
- Patch: Bugfix, kompatibel
- Minor: neue Features, kompatibel
- Major: Breaking Change, Migration noetig

Wenn dein Code gegen `stripe@^14.0.0` baut, holst du automatisch alle 14.x-Updates (Bugfixes, Features), nicht aber 15.x (Breaking).
