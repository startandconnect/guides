---
title: Modal / Dialog
---

# Modal / Dialog

Für destruktive Aktionen (Löschen, Storno), Formulare ohne eigene Seite (Refund, Korrektur anfordern), und Bestätigungen.

## Basis-Struktur

```tsx
<Dialog open={open} onOpenChange={setOpen}>
  <DialogContent className="max-w-lg">
    <DialogHeader>
      <DialogTitle>Titel</DialogTitle>
      <DialogDescription>Kurze Beschreibung der Aktion</DialogDescription>
    </DialogHeader>

    <div className="space-y-4">
      {/* Body */}
    </div>

    <DialogFooter>
      <Button variant="outline" onClick={() => setOpen(false)}>Abbrechen</Button>
      <Button onClick={handleConfirm} disabled={submitting}>
        {submitting ? <Spinner className="h-4 w-4" /> : <Icon className="h-4 w-4" />}
        Bestätigen
      </Button>
    </DialogFooter>
  </DialogContent>
</Dialog>
```

## Groessen

| Inhalt | max-w |
|---|---|
| Ja/Nein-Bestaetigung | `max-w-sm` |
| Kurzes Formular | `max-w-lg` |
| Laengeres Formular (mehrere Felder) | `max-w-2xl` |
| Komplexes Form mit Tabs | `max-w-4xl` |

## Destruktive Aktionen

```tsx
<Button onClick={handleDelete} disabled={loading} variant="destructive">
  {loading ? <Spinner className="h-4 w-4" /> : <Trash2 className="h-4 w-4" />}
  Endgültig löschen
</Button>
```

Eine destruktive Aktion MUSS:
- `variant="destructive"` am Button
- Checkbox oder freitext "Ich bestätige" bei wirklich unwiederbringbaren Aktionen
- Klare Beschreibung was passiert und was nicht mehr rückgängig gemacht werden kann

## Formular-Felder im Dialog

```tsx
<div className="space-y-2">
  <Label htmlFor="reason">Grund *</Label>
  <Select value={reason} onValueChange={setReason}>
    <SelectTrigger id="reason"><SelectValue /></SelectTrigger>
    <SelectContent>
      <SelectItem value="requested_by_customer">Kundenwunsch</SelectItem>
    </SelectContent>
  </Select>
</div>
```

Pflicht-Felder mit `<span className="text-destructive">*</span>` markieren.

## Don't do

- Kein Dialog-in-Dialog. Wenn ein zweiter Schritt nötig ist, den ersten schliessen und den zweiten öffnen.
- Keine Dialog ohne Footer-Buttons. Escape-Taste muss auch via Cancel funktionieren.
- Kein `autoFocus` auf dem Cancel-Button - das darf nur auf dem ersten Input oder Primary-Button.

## Verwendung im Code

- `apps/web/src/app/(team)/manage/invoices/[id]/page.tsx` (Refund + Korrektur)
- diverse Delete-Confirmations
