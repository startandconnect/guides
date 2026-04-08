---
title: HTML Override
order: 1
excerpt: Wie du eigenen HTML/CSS/JS-Code auf einer Seite verwendest
---

# HTML Override

Mit HTML Override kannst du eigenen HTML-, CSS- und JavaScript-Code direkt auf einer Seite verwenden. Ideal für KI-generierte Websites, Landingpages mit custom Animationen oder Seiten mit interaktiven Elementen.

## Modus wählen

Jede Seite hat zwei Override-Modi:

### Split-Modus (empfohlen)

HTML, CSS und JS sind getrennt:

- **HTML** — nur der Body-Inhalt (ohne `<html>`, `<head>` oder `<body>` Tags)
- **CSS** — Stylesheet, wird automatisch im `<head>` eingebunden
- **JavaScript** — Wird am Ende des Body eingebunden

Spotlight wrappt das Ganze automatisch in ein vollständiges HTML-Dokument mit den SEO-Einstellungen der Seite (Meta-Tags, Open Graph, Sitemap).

### Full-HTML-Modus

Ein komplettes HTML-Dokument mit `<!DOCTYPE html>`, `<head>`, `<body>` etc. Verwende das nur wenn du die SEO-Meta-Tags selbst setzen willst oder ganz eigene `<head>`-Inhalte brauchst.

## Externe Libraries einbinden

Du kannst externe Libraries per CDN laden — Spotlight hat keine Content-Security-Policy die das blockiert:

```html
<script src="https://cdn.jsdelivr.net/npm/alpinejs@3.x.x/dist/cdn.min.js" defer></script>
<script src="https://unpkg.com/htmx.org@latest"></script>
<link href="https://cdn.jsdelivr.net/npm/tailwindcss@4/dist/tailwind.min.css" rel="stylesheet">
```

## Media Library Referenzen

Bilder aus der [Media Library](/spotlight/guide/features/media-library) bindest du über ihre URL ein:

```html
<img src="/api/media/hero-image.jpg" alt="Hero">
```

## Credentials in JS nutzen

API-Keys aus [Credentials](/spotlight/guide/features/credentials) werden NIE direkt ins HTML geschrieben — sie würden sonst öffentlich sein. Stattdessen nutzt du die Proxy-Endpoints:

```js
// Beispiel: Brevo-Newsletter-Anmeldung
fetch('/api/proxy/brevo', {
  method: 'POST',
  headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify({ email: userEmail })
});
```

Der Server fügt den API-Key serverseitig hinzu. Mehr dazu unter [Credentials](/spotlight/guide/features/credentials).
