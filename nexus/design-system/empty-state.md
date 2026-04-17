---
title: Empty State
---

# Empty State

Was eine leere Liste oder ein leerer Bereich anzeigen soll.

## Basic Empty State

```tsx
<div className="flex flex-col items-center justify-center py-12 text-center">
  <div className="flex h-12 w-12 items-center justify-center rounded-full bg-muted mb-4">
    <Inbox className="h-6 w-6 text-muted-foreground" />
  </div>
  <p className="text-sm font-medium">Keine Einträge</p>
  <p className="text-xs text-muted-foreground mt-1">Sobald etwas passiert, erscheint es hier.</p>
</div>
```

## Mit Primary Action

```tsx
<div className="flex flex-col items-center justify-center py-12 text-center">
  <div className="flex h-12 w-12 items-center justify-center rounded-full bg-blue-50 text-blue-600 mb-4 dark:bg-blue-950">
    <Plus className="h-6 w-6" />
  </div>
  <p className="text-sm font-medium">Noch kein Kunde</p>
  <p className="text-xs text-muted-foreground mt-1 mb-4">
    Lege den ersten Kunden an um loszulegen.
  </p>
  <Button size="sm" onClick={createNew}>
    <Plus className="h-4 w-4" />
    Kunde anlegen
  </Button>
</div>
```

## Kurzform in Listen

Wenn der Empty-State ein unterkapitel einer Seite ist (nicht die ganze Seite):

```tsx
<p className="text-center text-muted-foreground py-8">Keine Einträge.</p>
```

## Regeln

- Icon in einem kreisförmigen Hintergrund (`h-12 w-12 rounded-full`), grau-muted für neutral, farbig bei "jetzt Aktion nötig".
- Zweizeilige Beschreibung: `font-medium` Zeile 1, `text-muted-foreground text-xs` Zeile 2.
- Primary Action nur wenn es aus dem Kontext heraus sinnvoll ist (z.B. "Kunde anlegen" in der Kundenliste).

## Don't do

- Keine großen Illustrationen/SVGs - ein Icon reicht.
- Kein "😔 Leider noch nichts" - Emojis sind im Admin Brand-off.
- Keine Links in den Empty-State-Text ohne passenden Kontext.
