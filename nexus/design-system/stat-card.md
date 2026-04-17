---
title: Stat Card
---

# Stat Card

Die einheitliche KPI-Card. Wird für alle Wert-Anzeigen in Dashboards, Detail-Seiten und Übersichten genutzt.

## Regeln

- **Padding**: immer `p-4` auf dem `CardContent`. Nicht p-5 oder p-6.
- **Icon-Container**: `h-10 w-10 rounded-lg` mit semantischer Hintergrundfarbe.
- **Icon**: `h-5 w-5` aus `lucide-react`.
- **Wert**: `text-xl font-bold`.
- **Label**: `text-xs text-muted-foreground`.
- **Layout**: Icon links, Text rechts (`flex items-center gap-4`).

## Code

```tsx
<Card>
  <CardContent className="flex items-center gap-4 p-4">
    <div className="flex h-10 w-10 items-center justify-center rounded-lg bg-blue-50 text-blue-600 dark:bg-blue-950">
      <DollarSign className="h-5 w-5" />
    </div>
    <div>
      <p className="text-xl font-bold">12.345 €</p>
      <p className="text-xs text-muted-foreground">Umsatz (30 Tage)</p>
    </div>
  </CardContent>
</Card>
```

## Farben pro Zweck

| Zweck | Light BG | Text | Dark BG |
|---|---|---|---|
| Primär/Balance | `bg-blue-50` | `text-blue-600` | `dark:bg-blue-950` |
| Positiv/Wachstum | `bg-green-50` | `text-green-600` | `dark:bg-green-950` |
| Revenue/Kosten | `bg-purple-50` | `text-purple-600` | `dark:bg-purple-950` |
| Warnung/Abo | `bg-orange-50` | `text-orange-600` | `dark:bg-orange-950` |
| Neutral/Info | `bg-gray-50` | `text-gray-600` | `dark:bg-gray-950` |

## Don't do

- Keine eigene Padding-Variante. Wenn die Card anders wirken muss, ist es keine Stat-Card, sondern ein anderes Pattern.
- Kein `text-2xl` oder `text-3xl` für den Wert. Das zerreißt die Konsistenz zwischen zwei nebeneinander stehenden Stat-Cards.
- Keine Graustufen als Icon-Hintergrund ausser für wirklich neutrale Infos.
- Keine Emojis als Icon.

## Verwendung im Code

Haupt-Nutzungsstellen:
- `apps/web/src/app/(team)/manage/dashboard/page.tsx`
- `apps/web/src/components/settings/logs-audit-section.tsx`
- diverse Detail-Seiten (Invoice, Order, Subscription)
