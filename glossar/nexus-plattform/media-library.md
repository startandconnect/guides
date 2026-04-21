---
title: Media Library
order: 20
excerpt: Zentraler Ort fuer Bilder, PDFs, Videos
---

# Media Library

Zentraler Upload-Ort fuer alle Medien in deiner Nexus-Instance. Bilder, PDFs, Videos, Audio, Dokumente.

## Wo finden

Admin unter `/manage/media`. Zeigt alle hochgeladenen Dateien als Grid mit Preview, Dateigroesse, Upload-Datum.

## Upload-Wege

- **Direkt per Drag-and-Drop** ins Media-Library-Grid
- **Pro Produkt** im Produkt-Editor (Featured Image, Gallery)
- **In Blog-Editor** beim Verfassen
- **In Page-Builder** fuer Sections
- **Per API** `POST /api/media-library`

## Storage

- **Lokal** (Container-Volume) - Default. Einfach aufzusetzen, skaliert bis 50-100 GB pro Instance.
- **S3** (konfigurierbar) - Hetzner Object Storage oder AWS S3. Fuer hohe Daten-Volumen oder Multi-Region-Zugriff.

Pro Instance per Settings entscheidbar. Nexus-SAC nutzt lokal; SUYL nutzt lokal; grosse Volumes wuerden auf S3 umsteigen.

## Media-Varianten

Bei Bild-Upload werden automatisch generiert:
- Thumbnails (mehrere Groessen)
- Webp-Version (bessere Compression)
- Resized fuer verschiedene Devices

Serviert werden sie als `next/image` mit responsive-srcset.

## Zugang

- **Admin** kann alle Files sehen/loeschen
- **Kunden** sehen nur Files die explizit zu ihnen geshared sind (Shared-Files-Feature)
- **Public Files** (z.B. Landing-Page-Bilder) sind ueber direkte URL abrufbar

## Organisation

Noch nicht: Folder-Struktur, Tags, Suche. Im Planning fuer naechsten Iteration. Aktuell: Files einfach als flache Liste mit Upload-Datum-Sortierung.

## Shared Files

Siehe separates Feature: Admin kann Files explizit an einen Kunden teilen. Erscheint im Customer-Portal unter `/customer/shared-files`. Tracking wann der Kunde das erste Mal heruntergeladen hat.

## Quota

Aktuell kein Quota pro Instance. Nexus-Pricing 99 Euro flat, inkl. "alles". Wenn eine Instance >100 GB nutzt wuerde, muesste Ben das individuell verhandeln (Outlier-Fall, bisher nie vorgekommen).
