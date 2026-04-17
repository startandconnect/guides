---
title: Farbpalette
---

# Farbpalette

Nexus nutzt Tailwind-Farben ohne Brand-spezifische Custom-Tokens. Semantische Zuordnung:

## Semantische Farben

| Semantik | Light | Dark | Einsatz |
|---|---|---|---|
| **Primär / Info / Balance** | `blue-50` bg / `blue-600` fg | `blue-950` bg / `blue-400` fg | Links, primäre KPIs, Info-Banner |
| **Positiv / Erfolg / Wachstum** | `green-50` bg / `green-600` fg | `green-950` bg / `green-400` fg | Paid, Active, Erfolg-Toast |
| **Revenue / Kosten / Highlight** | `purple-50` bg / `purple-600` fg | `purple-950` bg / `purple-400` fg | Umsatz-KPIs, Revenue-Charts |
| **Warnung / Aufmerksamkeit / Abo** | `orange-50` bg / `orange-600` fg | `orange-950` bg / `orange-400` fg | Pending, Warnung-Banner, Abo-Hinweis |
| **Destruktiv / Fehler** | `red-50` bg / `red-600` fg | `red-950` bg / `red-400` fg | Löschen, Fehler-Banner, Refund |
| **Neutral / Disabled** | `gray-50` bg / `gray-600` fg | `gray-900` bg / `gray-300` fg | Dezente Badges, Muted-Text-Umfeld |

## Dark-Mode Regel

Jede Farbverwendung braucht eine Dark-Variante:

```tsx
<div className="bg-blue-50 text-blue-600 dark:bg-blue-950 dark:text-blue-400">
```

## Tailwind-Scale

| Intensität | Hintergrund | Text |
|---|---|---|
| Sehr hell (Card-BG) | `*-50` | nicht als Text-Farbe |
| Hell (Badge-BG) | `*-100` | nicht als Text |
| Mittel | `*-600` | Standard-Brand-Text |
| Dunkel (Dark-BG) | `*-900`/`*-950` | nicht als Text |

## Keine eigenen Hex-Codes

- **Nie** `#2563EB` o.ä. im Code. Immer die Tailwind-Klasse.
- Einzige Ausnahme: PDF/Mail-Templates die kein Tailwind nutzen.

## Keine Zwischen-Farben

Nur diese Stufen verwenden: 50, 100, 200, 400, 600, 800, 900, 950. Keine `*-300` oder `*-700` - diese fallen optisch unsauber aus in der Mischpalette.

## Muted-Text (Paragraphs)

Immer `text-muted-foreground` für beschreibenden Text. Niemals eine Graustufe hartcodiert.

## Status-Badges

| Status | Variant |
|---|---|
| OK / Paid / Active / Success | `success` |
| Pending / Warning / Canceling | `warning` |
| Failed / Refunded / Destructive | `destructive` |
| Draft / Inactive / Neutral | `secondary` |

Die Variants sind in `components/ui/badge.tsx` definiert. Nicht eigene Farb-Klassen auf dem Badge inline setzen.
