---
title: Info / Success / Warning Banner
---

# Banner

Hinweis-Banner für kontextuelle Infos oberhalb oder innerhalb von Karten.

## Info-Banner

```tsx
<div className="flex items-start gap-3 rounded-lg border border-blue-200 bg-blue-50 p-4 dark:border-blue-900 dark:bg-blue-950">
  <Info className="h-5 w-5 text-blue-600 flex-shrink-0 mt-0.5" />
  <div className="text-sm">
    <p className="font-medium text-blue-800 dark:text-blue-200">Titel</p>
    <p className="text-blue-600 dark:text-blue-400 mt-1">Beschreibung</p>
  </div>
</div>
```

## Erfolg-Banner

```tsx
<div className="flex items-center gap-3 rounded-lg border border-green-200 bg-green-50 p-4 dark:border-green-900 dark:bg-green-950">
  <CheckCircle2 className="h-5 w-5 text-green-600 flex-shrink-0" />
  <p className="text-sm font-medium text-green-800 dark:text-green-200">Message</p>
</div>
```

## Warnung-Banner

```tsx
<div className="flex items-start gap-3 rounded-lg border border-orange-200 bg-orange-50 p-4 dark:border-orange-900 dark:bg-orange-950">
  <AlertTriangle className="h-5 w-5 text-orange-600 flex-shrink-0 mt-0.5" />
  <div className="text-sm">
    <p className="font-medium text-orange-800 dark:text-orange-200">Achtung</p>
    <p className="text-orange-600 dark:text-orange-400 mt-1">Details</p>
  </div>
</div>
```

## Error/Destructive-Banner

```tsx
<div className="flex items-start gap-3 rounded-lg border border-red-200 bg-red-50 p-4 dark:border-red-900 dark:bg-red-950">
  <XCircle className="h-5 w-5 text-red-600 flex-shrink-0 mt-0.5" />
  <div className="text-sm">
    <p className="font-medium text-red-800 dark:text-red-200">Fehler</p>
    <p className="text-red-600 dark:text-red-400 mt-1">Details</p>
  </div>
</div>
```

## Regeln

- Ein Icon aus `lucide-react`, `h-5 w-5`, `flex-shrink-0`.
- Einzeilige Banner: `flex items-center`.
- Mehrzeilige Banner (Titel + Desc): `flex items-start` + `mt-0.5` für Icon-Alignment.
- Padding `p-4`.
- `rounded-lg border` mit farbpassendem `border-*-200`/`border-*-900`.

## Don't do

- Keine Banner ohne Icon.
- Kein `px-6` oder ähnliche Abweichungen vom `p-4` Standard.
- Kein eigenes `font-size: 16px` o.ä. - immer `text-sm`.
