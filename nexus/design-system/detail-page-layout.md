---
title: Detail Page Layout
---

# Detail Page Layout

Einheitliches Layout für Detailseiten (Invoice, Order, Customer, Product, Deal).

## Struktur

1. **Zurück-Button** (mit `ArrowLeft`, Link zur Liste)
2. **Kopf-Card**: Titel + Status-Badge + Primary-Actions rechts
3. **Content-Cards**: eine Card pro logisch zusammengehörigem Abschnitt (Items, Zahlungen, Rechnungsadresse, Verknüpfungen)
4. **Änderungshistorie** (AuditLog-Tab, Sprint 2.2) wenn relevant

## Kopf-Card

```tsx
<Card>
  <CardHeader>
    <div className="flex items-start justify-between">
      <div className="space-y-1">
        <CardTitle className="flex items-center gap-2">
          {title}
          <Badge variant={statusVariants[status]}>{statusLabels[status]}</Badge>
        </CardTitle>
        <CardDescription>{description}</CardDescription>
      </div>
      <div className="flex gap-2">
        <Button variant="outline">Action 1</Button>
        <Button variant="destructive">Action 2</Button>
      </div>
    </div>
  </CardHeader>
  <CardContent>...</CardContent>
</Card>
```

## Abschnitte innerhalb einer Card

Wenn eine Card mehrere Sub-Abschnitte enthält:

```tsx
<div className="rounded-lg border p-4 space-y-3">
  <div>
    <p className="font-medium">{title}</p>
    <p className="text-xs text-muted-foreground">{description}</p>
  </div>
  {/* Content */}
</div>
```

## Spacing

- Card-zu-Card Abstand: `space-y-4` oder `mt-4`
- Innerhalb Card: `space-y-6` für Sub-Abschnitte
- Dense Tables: `py-2` zwischen Rows

## Änderungshistorie einhängen

Am Ende der Detail-Seite, nach den fachlichen Cards:

```tsx
<Card className="mt-4">
  <CardHeader>
    <CardTitle>Änderungshistorie</CardTitle>
    <CardDescription>Alle Änderungen aus dem Audit-Log.</CardDescription>
  </CardHeader>
  <CardContent>
    <AuditLogTab entity="invoice" entityId={invoice.id} />
  </CardContent>
</Card>
```

## Verwendung im Code

- `apps/web/src/app/(team)/manage/invoices/[id]/page.tsx`
- `apps/web/src/app/(team)/manage/orders/[id]/page.tsx`
- `apps/web/src/app/(team)/manage/subscriptions/[id]/page.tsx`
