---
title: Erste Seite anlegen
order: 2
excerpt: Code reinkopieren, Vorschau, live schalten - in unter 5 Minuten
---

# Erste Seite anlegen

Du hast deine Website mit Claude, ChatGPT oder v0 erstellt? Perfekt. So bringst du sie live.

## Neue Seite erstellen

1. Im Admin links auf **Seiten** klicken
2. Oben rechts auf **Neue Seite**
3. Titel und Slug eintragen:
   - **Titel** — z.B. `Startseite`
   - **Slug** — z.B. `home` (oder leer lassen für die Hauptseite)

## HTML einfügen

Im Editor hast du zwei Modi:

### HTML-Override (empfohlen für KI-Code)

Im Tab **HTML Override**:

1. **Modus** auf `Split` stellen (HTML, CSS und JS getrennt)
2. Deinen HTML-Code in das HTML-Feld
3. CSS in das Style-Feld
4. JavaScript in das Script-Feld

Oder **Modus** auf `Full HTML` — dann packst du einen kompletten HTML-Dokumenten mit `<head>`, `<body>` etc. in ein einziges Feld.

### Visueller Editor

Im Tab **Sections** baust du Seiten mit vorgefertigten Blöcken (Hero, Features, FAQ, CTA). Ideal für schnelle Landingpages ohne KI-Code.

## Vorschau

Oben rechts auf **Vorschau** — öffnet deine Seite in einem neuen Tab, noch bevor sie live ist.

## Veröffentlichen

Wenn alles passt: **Status** auf `Veröffentlicht` stellen → **Speichern**. Deine Seite ist sofort live unter `deine-domain.com/<slug>`.

> Tipp: Für die Startseite setze den Slug auf `home` und markier sie als **Default Page** in den Seiten-Einstellungen. Dann wird sie unter `deine-domain.com/` angezeigt.

## JavaScript & externe Libraries

Spotlight hostet JavaScript direkt — du kannst also:

- Alpine.js, htmx, GSAP, Three.js etc. per CDN einbinden
- `fetch()` auf externe APIs machen
- LocalStorage, SessionStorage nutzen
- Custom Animationen, Quizze, Interaktionen

Wenn du API-Keys brauchst (z.B. für OpenAI oder Brevo), leg sie unter **[Credentials](/spotlight/guide/features/credentials)** ab.
