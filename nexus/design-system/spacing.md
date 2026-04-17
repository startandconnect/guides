---
title: Spacing
---

# Spacing

Abstände im Nexus-Admin folgen Tailwind-Spacing-Skala mit enger Beschränkung auf wenige Werte.

## Allgemeine Regel

> Wenn du unsicher bist: `p-4`, `gap-4`, `space-y-4` sind die Defaults.

## Padding in Cards

| Card-Typ | Padding |
|---|---|
| Stat-Card | `p-4` |
| Header-Card (mit CardHeader) | `px-6 py-4` (Standard-Shadcn) |
| Dense-List-Row | `p-3` |

## Gaps (Horizontal)

| Zweck | Class |
|---|---|
| Stat-Card zu Stat-Card | `gap-4` |
| Icon zu Text | `gap-3` |
| Button-Gruppen | `gap-2` |
| Filter-Bar Items | `gap-3` |

## Space-Y (Vertikal)

| Zweck | Class |
|---|---|
| Top-Level Seiten-Sections | `space-y-6` |
| Card-zu-Card in einer Section | `space-y-4` |
| Form-Felder untereinander | `space-y-2` |
| Dense-List (Audit-Rows) | `space-y-2` |

## Padding innerhalb Content

| Zweck | Class |
|---|---|
| Page-Wrapper | `p-6` oder `p-8` je nach Seite, einheitlich pro Seite halten |
| Card-Content Default | `p-4` oder Shadcn-Standard |
| Inline-Codes/Pre | `p-2` |

## Abstands-Anti-Patterns

- **Nie** `mt-1 mb-3` u.ä. kombinieren. Wenn `space-y-*` auf dem Parent sitzt, braucht das Child kein `mt`.
- **Nie** Pixelwerte wie `pt-[11px]`. Wenn die Skala nicht reicht, ist das Layout zu eng.
- **Nie** `px-4 py-3.5` - immer symmetrische Paare (`p-4`, `px-4 py-4`, `px-6 py-4`).

## Mobile Breakpoints

- Standard-Layout ist mobile-first, Desktop-Styles via `md:`-Prefix.
- Zwischen Cards: auf Mobile `space-y-4`, Desktop `grid gap-4 sm:grid-cols-2 lg:grid-cols-3`.
- Filter-Bar `flex flex-wrap` mit `gap-3` - wraps automatisch auf Mobile.
