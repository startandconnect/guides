---
title: Advanced
order: 8
excerpt: Wenn die Basis sitzt - Auto-Sync, Skills, externe Integrationen, Multi-Device
---

# Advanced

Dieser Abschnitt ist erst relevant wenn dein Second Brain seit mindestens 4 Wochen läuft. Vorher nicht reinschauen - du wirst nur kompliziert wo einfach reicht.

## Auto-Sync zwischen Geräten

Wenn du an mehreren Rechnern arbeitest (Laptop, Desktop, Arbeit, privat), willst du nicht manuell pullen und pushen.

### Option A: Launchd (Mac) oder systemd (Linux)

Ein Job der alle 5 Minuten automatisch pullt und pusht.

TODO: Konkrete Scripts mit `git pull --rebase && git push`.

### Option B: Obsidian Git Plugin

Obsidian als Editor, Plugin synct automatisch im Hintergrund. Funktioniert auch auf Mobile mit Obsidian Mobile.

### Option C: GitHub Actions

Wenn du spezielle Checks willst (Linter, Spell-Check, Link-Checker), kannst du GitHub Actions nutzen. Aber: meistens overkill für ein Wiki.

TODO: Minimales Setup pro Option.

## Skills für Wiederkehrendes

Claude Code Skills automatisieren Routine-Aufgaben im Wiki. Beispiele:

- **`/tagesstart`** - liest Wiki, fragt nach Prioritäten, legt daily-Datei an
- **`/projekt-init <name>`** - legt Projekt-Ordner mit context.md-Template an
- **`/wochenabschluss`** - zieht daily-Dateien der Woche zusammen, aktualisiert Projekte
- **`/inbox-sortieren`** - nimmt inbox.md und schlägt Einsortierung vor

Details zum Bau von Skills: [[../claude-code/skills-hooks-subagents|Skills, Hooks und Subagents]].

TODO: Ein Skill hier komplett dokumentieren als Referenzbeispiel.

## Hooks für Disziplin

Ein Hook der bei jedem Session-Ende prüft ob die Session-Datei aktualisiert wurde. Einer der bei jedem Commit einen Sanity-Check fährt.

TODO: Beispiel-Hook für Wiki-Pflege.

## MCP Server für Wiki-Integration

Wenn du einen MCP Server baust der dein Wiki versteht (Suche, Tags, Graph), bekommt Claude Code einen strukturierten Zugang zu deinem Wissen - nicht nur "lies Datei X" sondern "finde alle Notizen zu Thema Y".

Warnung: eher ein Wochenende-Projekt, kein Must-Have.

TODO: Link auf MCP-Doku wenn relevant.

## Externe Integrationen

### Notion / Obsidian als zusätzlicher Viewer

Wenn du visuell lesen willst, kannst du deinen Wiki-Ordner als Notion-Import nutzen oder in Obsidian öffnen. Die Markdown-Dateien funktionieren in beiden. Obsidian ist stärker weil es direkt mit dem Ordner arbeitet.

### Kalender-Anbindung

Für Morning Routine: Calendar-API fragen, Termine in daily-Datei einfügen. Als Skill oder Shortcut.

### Newsletter / Blog aus dem Wiki speisen

Inhalte aus reference/ oder projects/ als Quellmaterial für Blog-Posts nutzen. Claude Code liest Wiki, schreibt Entwurf, du finalisierst.

TODO: Workflow-Beispiel.

## Multi-User Wikis (Teams)

Möglich, aber mit Fallstricken:

- Pro Person eigener Branch? Meist zu viel Overhead.
- Einfacher: ein gemeinsames main, klarer Ownership pro Ordner/Datei.
- Konventionen müssen glasklar sein, sonst entsteht Chaos.

Für Teams ab 3 Personen würde ich ein dediziertes Wiki-Tool (Outline, BookStack) in Betracht ziehen statt Markdown-Repo.

## Was du dir nicht antun solltest

- **Zu viele Plugins installieren.** Je mehr Tooling, desto mehr Wartung.
- **Perfekte Strukturen in der Theorie entwerfen.** Aus Use-Cases wachsen, nicht aus Diagrammen.
- **Dein Wiki als Content-Maschine missbrauchen.** Es ist Second Brain, nicht Blogsoftware.

:::tip[Meta]
Alles hier ist optional. Dein Second Brain ist dann am wertvollsten, wenn du es wirklich nutzt - nicht wenn es am meisten Features hat.
:::
