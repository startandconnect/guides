---
title: Cookie-Banner
order: 4
excerpt: DSGVO-konformer Cookie-Consent ohne externe Tools
---

# Cookie-Banner

Spotlight hat einen eingebauten Cookie-Banner, der DSGVO-konform ist und ohne externe Tools wie Cookiebot oder Usercentrics auskommt.

## Aktivieren

1. Gehe zu **Einstellungen > Cookie-Banner**
2. Schalte `Cookie-Banner aktiv` ein
3. Text und Farben anpassen (optional)
4. Speichern

Der Banner erscheint automatisch bei jedem neuen Besucher.

## Kategorien

Der Banner unterstützt drei Kategorien:

- **Notwendig** — Immer aktiv, kann nicht deaktiviert werden (Session-Cookies etc.)
- **Statistik** — Opt-in für Analytics (z.B. Plausible, Umami)
- **Marketing** — Opt-in für Tracking-Pixel (z.B. Facebook, Google Ads)

Nutzer können pro Kategorie entscheiden.

## Scripts erst nach Einwilligung laden

Damit dein Analytics-Script erst nach Consent geladen wird, nutzt du das `data-consent` Attribut:

```html
<!-- Wird erst geladen wenn "statistik" akzeptiert wurde -->
<script data-consent="statistik" src="https://plausible.io/js/plausible.js"></script>

<!-- Wird erst geladen wenn "marketing" akzeptiert wurde -->
<script data-consent="marketing" src="https://connect.facebook.net/en_US/fbevents.js"></script>
```

Spotlight wartet automatisch auf die Einwilligung und lädt das Script erst dann.

## Consent im JavaScript prüfen

Wenn du eigene Logik basierend auf dem Consent brauchst:

```js
// Aktueller Consent-State
const consent = window.spotlightConsent.get();
// { necessary: true, statistik: false, marketing: false }

if (consent.statistik) {
  // Analytics-Code
}

// Auf Änderung reagieren
window.addEventListener('spotlight-consent-change', (e) => {
  console.log('Consent geändert:', e.detail);
});
```

## Consent zurücksetzen

Der Nutzer kann seine Entscheidung jederzeit ändern — füge einen Link ins Footer ein:

```html
<a href="#" onclick="window.spotlightConsent.open(); return false;">
  Cookie-Einstellungen
</a>
```

Das öffnet den Banner erneut.

## Impressum & Datenschutz

Der Banner verlinkt automatisch auf deine **Impressum** und **Datenschutzerklärung** Seiten (siehe [Rechtliches](/spotlight/guide/rechtliches/impressum)). Die beiden Seiten musst du aber selbst befüllen — Spotlight kann das nicht für dich.
