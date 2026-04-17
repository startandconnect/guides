---
title: List Page Template
---

# List Page Template

Standard-Layout für alle Admin-Listen: Orders, Invoices, Customers, Products, Deals, Audit-Log etc.

## Struktur

1. **Header** (page title + Primary-Action-Button)
2. **Stats-Row** (1-4 Stat-Cards)
3. **Filter-Bar** (Search-Input + Dropdowns + Reload-Button)
4. **Liste** in einer Card
5. **Pagination** am Ende der Liste

```
+-----------------------------------+
| Page Title              [+ New]   |
+-----------------------------------+
| [StatCard] [StatCard] [StatCard]  |
+-----------------------------------+
| [Search...] [Filter] [↻]         |
+-----------------------------------+
| Card                              |
|   • Row 1                         |
|   • Row 2                         |
|   • Row 3                         |
|                                   |
|     ← Prev  [2 von 5]  Next →     |
+-----------------------------------+
```

## Wichtige Regeln

- Header unterhalb des globalen `<Header />` Komponenten, NIE eine eigene Nav.
- Stats-Row nur anzeigen wenn es mindestens zwei sinnvolle Werte gibt. Bei einem einzelnen Wert direkt ohne Stats-Row starten.
- Filter-Bar immer eine Zeile, auf kleinen Screens wraps. Dropdown-Breiten 140-180px.
- Liste als `<Card>` gewrapped mit `<CardHeader>` (Titel) und `<CardContent>` (Zeilen oder Table).
- Row-Hover immer `hover:bg-muted/50`.
- Pagination nur anzeigen, wenn mehr als eine Seite existiert.

## Beispiel

```tsx
<div className="space-y-6">
  <div className="grid gap-4 sm:grid-cols-3">
    <Card><CardContent className="p-4">...</CardContent></Card>
    <Card><CardContent className="p-4">...</CardContent></Card>
    <Card><CardContent className="p-4">...</CardContent></Card>
  </div>
  <div className="flex flex-wrap items-center gap-3">
    <Input placeholder="Suchen..." />
    <Select>...</Select>
    <Button variant="outline" size="sm"><RefreshCw /></Button>
  </div>
  <Card>
    <CardHeader><CardTitle>Titel</CardTitle></CardHeader>
    <CardContent>...</CardContent>
  </Card>
</div>
```

## Verwendung im Code

- `apps/web/src/components/settings/logs-audit-section.tsx`
- `apps/web/src/app/(team)/manage/invoices/page.tsx`
- `apps/web/src/app/(team)/manage/orders/page.tsx`
