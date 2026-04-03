---
title: window.nx API
order: 2
excerpt: JavaScript API für HTML-Override Seiten
---

# window.nx API

Wenn du eigene HTML-Seiten über den HTML-Override baust, hast du Zugriff auf die `window.nx` API. Damit kannst du auf Nexus-Features zugreifen ohne eigene API-Calls zu machen.

## Verfügbare Module

```javascript
window.nx.theme      // Theme & Dark Mode
window.nx.products   // Produkte laden
window.nx.checkout   // Checkout öffnen
window.nx.blog       // Blog-Artikel laden
window.nx.reviews    // Reviews laden
window.nx.events     // Events laden
```

## Theme / Dark Mode

```javascript
// Aktuelles Theme lesen
nx.theme.current  // 'dark' oder 'light'

// Theme setzen
nx.theme.set('dark')
nx.theme.set('light')

// Toggle
nx.theme.toggle()

// Auf Änderungen reagieren
nx.theme.onChange(function(theme) {
  console.log('Theme gewechselt:', theme)
})
```

## Checkout öffnen

Verlinke auf `#checkout:produkt-slug` um den Checkout als Overlay zu öffnen:

```html
<a href="#checkout:mein-produkt">Jetzt kaufen</a>
```

Mit spezifischem Preis:

```html
<a href="#checkout:mein-produkt:preis-id">Jahresabo wählen</a>
```

## Produkte laden

```javascript
// Alle Produkte
var products = await nx.products.list()

// Einzelnes Produkt
var product = await nx.products.get('produkt-slug')
```

## Blog-Artikel laden

```javascript
// Aktuelle Artikel
var posts = await nx.blog.list({ limit: 5 })

// Einzelner Artikel
var post = await nx.blog.get('artikel-slug')
```

:::info[Nur in HTML-Override]
Die `window.nx` API ist nur verfügbar wenn deine Seite als HTML-Override in Nexus läuft. Auf externen Websites nutze stattdessen die REST-API mit API Key.
:::
