---
title: Filter Bar
---

# Filter Bar

Die horizontale Filter-Leiste über Listen. Kombiniert Search, Dropdown-Filter und Actions.

## Regeln

- Eine Zeile, wraps auf kleinen Screens (`flex flex-wrap items-center gap-3`).
- Search ganz links, flex-grow (`flex-1 min-w-[200px]`).
- Dropdowns rechts davon, feste Breite 140-180px.
- Actions (Refresh, Export, +New) ganz rechts, als `Button variant="outline" size="sm"`.
- Search mit Icon links (`Search` aus `lucide-react`), Input mit `pl-9`.

## Code

```tsx
<div className="flex flex-wrap items-center gap-3">
  <div className="relative flex-1 min-w-[200px]">
    <Search className="absolute left-3 top-1/2 h-4 w-4 -translate-y-1/2 text-muted-foreground" />
    <Input
      placeholder="Suchen..."
      value={search}
      onChange={(e) => { setSearch(e.target.value); setOffset(0); }}
      className="pl-9"
    />
  </div>

  <Select value={statusFilter} onValueChange={setStatusFilter}>
    <SelectTrigger className="w-[160px]"><SelectValue placeholder="Alle" /></SelectTrigger>
    <SelectContent>
      <SelectItem value="">Alle</SelectItem>
      <SelectItem value="PAID">Bezahlt</SelectItem>
      <SelectItem value="OPEN">Offen</SelectItem>
    </SelectContent>
  </Select>

  <Button variant="outline" size="sm" onClick={reload}>
    <RefreshCw className={cn('h-4 w-4', loading && 'animate-spin')} />
  </Button>
  <Button variant="outline" size="sm" onClick={exportCsv}>
    <Download className="h-4 w-4" /> CSV
  </Button>
</div>
```

## Debounced Search

Free-text-Search immer mit 300ms Debounce:

```tsx
const [search, setSearch] = React.useState('');
const [debouncedSearch, setDebouncedSearch] = React.useState('');
React.useEffect(() => {
  const t = setTimeout(() => setDebouncedSearch(search), 300);
  return () => clearTimeout(t);
}, [search]);
```

Die `loadXxx` useCallback-Dependency nutzt `debouncedSearch`, nicht `search` direkt.

## Don't do

- Kein eigenes Filter-Modal statt der Dropdown-Kette. Modal ist erst sinnvoll wenn mehr als 5 Filter gleichzeitig aktiv sein können.
- Kein "Apply Filter"-Button. Filter greifen onChange. Der Refresh-Button ist nur für manuelle Reloads da.

## Verwendung im Code

- `apps/web/src/components/settings/logs-audit-section.tsx`
- `apps/web/src/app/(team)/manage/orders/page.tsx`
- `apps/web/src/app/(team)/manage/invoices/page.tsx`
