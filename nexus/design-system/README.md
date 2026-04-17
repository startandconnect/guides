# Design-System

Quelle der Wahrheit für UI-Patterns im Nexus-Admin und Customer-Portal. Wer eine neue Seite baut, schaut hier rein und benutzt die bestehenden Bausteine, statt sich eigene Stile auszudenken.

## Prinzipien

1. **Konsistenz vor Individualität.** Eine Detail-Seite sieht auf jeder Seite gleich aus. Ein Filter-Bar sieht auf jeder Liste gleich aus.
2. **Compact.** Viel Information auf wenig Platz. Keine übertriebenen Paddings, keine riesigen Hero-Elemente im Admin.
3. **Farbcodiert.** KPIs, Badges und Banner haben semantische Farben (blau = Info/Primär, grün = Positiv, rot = Warnung, orange = Abo/Aufmerksamkeit).
4. **Dark-Mode first-class.** Jeder neue Baustein braucht sowohl Light- als auch Dark-Mode-Styles.
5. **Mobil respektiert.** Tabellen haben ein Mobile-Layout (Kacheln statt Spalten).

## Aktueller Umfang

| Pattern | Status | Seite |
|---|---|---|
| Stat Card | standardisiert | [stat-card.md](./stat-card.md) |
| List Page Template | standardisiert | [list-page-template.md](./list-page-template.md) |
| Detail Page Layout | standardisiert | [detail-page-layout.md](./detail-page-layout.md) |
| Filter Bar | standardisiert | [filter-bar.md](./filter-bar.md) |
| Info/Success/Warning Banner | standardisiert | [banners.md](./banners.md) |
| Modal / Dialog | standardisiert | [modal-dialog.md](./modal-dialog.md) |
| Empty State | standardisiert | [empty-state.md](./empty-state.md) |
| Diff View (Audit-Log) | standardisiert | [diff-view.md](./diff-view.md) |
| Spacing | Regelwerk | [spacing.md](./spacing.md) |
| Farbpalette | Regelwerk | [colors.md](./colors.md) |
| Typografie | Regelwerk | [typography.md](./typography.md) |

## Was hier nicht steht

- Brand-Richtlinien der Start-&-Connect-Marke (Logo, Corporate-Farben). Das lebt in `brand/`.
- Shadcn-UI-Komponenten selbst (Card, Button, Input, etc.). Die Low-Level-Dokumentation steht auf [ui.shadcn.com](https://ui.shadcn.com/).

## Wann dieses Guide fertig ist

Nie. Jedes neue Pattern ergänzt hier eine Seite, wenn es an mindestens zwei Stellen im Code auftaucht.
