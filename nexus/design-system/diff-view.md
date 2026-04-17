---
title: Diff View (Audit-Log)
---

# Diff View

Vorher/Nachher-Anzeige für das Audit-Log und andere Änderungs-Historien. Feldweise 3-Spalten-Grid.

## Code

```tsx
<div className="rounded border divide-y text-xs">
  <div className="grid grid-cols-[120px_1fr_1fr] gap-2 px-2 py-1.5 font-medium bg-muted">
    <span>Feld</span>
    <span>Vorher</span>
    <span>Nachher</span>
  </div>
  {changedFields.map((key) => (
    <div key={key} className="grid grid-cols-[120px_1fr_1fr] gap-2 px-2 py-1.5 font-mono">
      <span className="font-sans font-medium truncate">{key}</span>
      <span className="text-red-600 dark:text-red-400 break-all">{formatValue(before?.[key])}</span>
      <span className="text-green-600 dark:text-green-400 break-all">{formatValue(after?.[key])}</span>
    </div>
  ))}
</div>
```

## Regeln

- **Grid**: `grid-cols-[120px_1fr_1fr]` - fixed Feldname links, Vorher und Nachher gleich breit.
- **Vorher-Spalte**: `text-red-600 dark:text-red-400`.
- **Nachher-Spalte**: `text-green-600 dark:text-green-400`.
- **Font**: `font-mono` für Werte, `font-sans` für Feldnamen.
- **Break-all**: Lange JSON-Werte dürfen brechen (`break-all`).
- **Skip**: `createdAt`/`updatedAt` aus der Anzeige filtern (Prisma-Noise).

## Wann Diff-View nicht angezeigt wird

Der `LogsAuditSection` rendert:
- "Keine Feldwerte haben sich geändert" wenn `changedFields.length === 0` (no-op update)
- "Kein Vorher/Nachher-Snapshot" wenn weder `beforeData` noch `afterData` vorhanden (z.B. manuelle audit.log-Aufrufe wie USER_LOGIN)

## Value-Formatierung

```tsx
function formatValue(v: unknown): string {
  if (v === null || v === undefined) return '-';
  if (typeof v === 'object') return JSON.stringify(v);
  return String(v);
}
```

## Verwendung im Code

- `apps/web/src/components/settings/logs-audit-section.tsx` (Audit-Log-Hauptseite)
- `apps/web/src/components/audit-log/AuditLogTab.tsx` (Per-Entity-Tab auf Detail-Seiten)
