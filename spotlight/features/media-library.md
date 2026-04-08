---
title: Media Library
order: 1
excerpt: Bilder, Videos und Downloads verwalten
---

# Media Library

In der Media Library verwaltest du alle Dateien deiner Website — Bilder, Videos, PDFs, Downloads.

## Dateien hochladen

1. Gehe zu **Media** im Seitenmenü
2. Dateien per Drag & Drop in das Upload-Feld ziehen — oder auf **Hochladen** klicken
3. Alle gängigen Formate werden unterstützt:
   - **Bilder** — JPG, PNG, WebP, GIF, SVG
   - **Videos** — MP4, WebM
   - **Dokumente** — PDF, DOCX, XLSX
   - **Archive** — ZIP

## In HTML verwenden

Jede Datei bekommt eine eindeutige URL. Du kannst sie so einbinden:

```html
<img src="/api/media/mein-bild.jpg" alt="Beschreibung">
<video src="/api/media/demo-video.mp4" controls></video>
<a href="/api/media/broschuere.pdf" download>PDF herunterladen</a>
```

Oder mit der Media-ID:

```html
<img src="/api/media/{media-id}" alt="Beschreibung">
```

## Organisieren

- **Ordner** — Erstelle Ordner zur Gruppierung (z.B. `hero`, `produkte`, `blog`)
- **Tags** — Mehrere Tags pro Datei für bessere Suche
- **Suche** — Nach Dateiname oder Tag

## Bild-Optimierung

Spotlight liefert Bilder automatisch optimiert aus:

- **WebP-Konvertierung** on-the-fly für moderne Browser
- **Responsive Größen** via `srcset`:

```html
<img
  src="/api/media/hero.jpg?w=1200"
  srcset="/api/media/hero.jpg?w=400 400w,
          /api/media/hero.jpg?w=800 800w,
          /api/media/hero.jpg?w=1200 1200w"
  sizes="(max-width: 768px) 100vw, 50vw"
  alt="Hero">
```

## Storage-Limits

- **Einzelne Datei** — max. 50 MB
- **Gesamt** — unbegrenzt (fair use)

Für Videos über 50 MB empfehlen wir externe Hosting-Dienste wie Vimeo oder YouTube.
