---
title: Command Palette
order: 18
excerpt: Cmd+K fuer schnellen Zugang zu allem
---

# Command Palette

Tastatur-Shortcut-Dialog im Admin-Bereich. Cmd+K auf Mac, Ctrl+K auf Windows. Oeffnet ein Suchfeld mit Zugang zu allen Pages, Actions, Entities.

## Was man damit macht

- **Navigation** - "Produkte" tippen → Enter → bin auf Produkt-Liste
- **Quick-Actions** - "Neues Produkt" → Dialog oeffnet sich
- **Entity-Search** - "Max Mustermann" → findet den Kunden
- **Recent** - letzte 5 besuchte Seiten als Vorschlag

## Fuzzy-Search

Du musst nicht exakt tippen. "prodh" findet "Produkte hochladen". "customor overvio" findet "Customer Overview". Score basiert auf Label + Keywords.

## Quick-Actions

Vordefinierte Shortcuts fuer haeufige Create-Flows:
- Neues Produkt
- Neuer Gutschein
- Neue Seite
- Neue Nachricht
- Neues Formular
- Neuer Blog-Post

Fuehren via `?new=1` Query-Param zu einer Route und triggern dort das Create-Modal.

## Entity-Search

Live-Suche gegen Backend-APIs (debounced 200ms):
- `/api/customers` - Kunden finden
- `/api/products` - Produkte finden
- `/api/orders` - Bestellungen finden

Eingegebener String wird per Token-AND-Search gegen mehrere Felder gematcht. Z.B. "ben scheurer" findet Kunden mit firstName=Ben und lastName=Scheurer auch wenn getrennt gespeichert.

## Recent Items

Die letzten 5 besuchten Seiten via localStorage. Verschwinden nicht zwischen Sessions - aber sind browser-lokal (auf Handy andere als Desktop).

## Tastatur-Navigation

- Pfeil-Hoch/Runter - durch Results navigieren
- Enter - selektiertes oeffnen
- Escape - Palette schliessen
- Tab - zwischen Kategorien springen (wenn mehrere)

## Warum so wichtig

Bei >500 Admin-Features kommst du per Sidebar irgendwann nicht mehr nach. Command Palette skaliert - egal wieviele Features, Tipp-Tipp-Enter bleibt gleich schnell.

Entspricht dem Pattern von VSCode, Slack, Linear, Raycast - mittlerweile Standard fuer produktive Tools.
