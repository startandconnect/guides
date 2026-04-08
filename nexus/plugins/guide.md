---
title: Guide
order: 13
excerpt: Produktdokumentation aus Git-Repositories als öffentliche Wissensdatenbank
---

# Guide

Betreibe eine öffentliche Produktdokumentation direkt in Nexus. Verbinde ein Git-Repository und Nexus rendert deine Markdown-Dateien als navigierbare Wissensdatenbank.

## Git-Repository anbinden

1. Gehe zu **Einstellungen > Plugins > Guide**
2. Trage die URL deines GitHub-Repositories ein
3. Konfiguriere den Branch (Standard: `main`)
4. Nexus klont das Repository und rendert die Markdown-Dateien

:::info[Hinweis]
Aktuell wird GitHub als Git-Provider unterstützt. Das Repository kann öffentlich oder privat sein - bei privaten Repos brauchst du einen Access Token.
:::

## Ordnerstruktur = Navigation

Die Ordnerstruktur in deinem Repository wird direkt zur Sidebar-Navigation:

```
docs/
  erste-schritte/
    _meta.json
    installation.md
    konfiguration.md
  plugins/
    _meta.json
    übersicht.md
    blog.md
```

Jeder Ordner wird zu einer Sektion, jede Markdown-Datei zu einer Seite.

### _meta.json

Mit `_meta.json` steuerst du Titel, Reihenfolge und Icons pro Ordner:

```json
{
  "title": "Erste Schritte",
  "order": 1,
  "icon": "rocket"
}
```

- **title** - Der angezeigte Name in der Navigation
- **order** - Sortierung (aufsteigend)
- **icon** - Optional ein Icon aus der verfügbaren Icon-Bibliothek

## Markdown mit Frontmatter

Jede Seite ist eine Markdown-Datei mit Frontmatter:

```markdown
---
title: Installation
order: 1
excerpt: So installierst du Nexus
---

# Installation

Hier beginnt der Inhalt...
```

- **title** - Seitentitel in der Navigation
- **order** - Reihenfolge innerhalb des Ordners
- **excerpt** - Kurzbeschreibung (wird in Übersichten angezeigt)

## Unterstützte Formate

### Syntax-Highlighting

Code-Blöcke werden mit Shiki gerendert und unterstützen alle gängigen Sprachen:

````markdown
```javascript
const greeting = "Hallo Welt";
console.log(greeting);
```
````

### Callouts

Vier Callout-Typen für wichtige Hinweise:

```markdown
:::tip[Tipp]
Ein hilfreicher Tipp für den Leser.
:::

:::info[Hinweis]
Eine allgemeine Information.
:::

:::warning[Wichtig]
Eine Warnung auf die man achten sollte.
:::

:::danger[Achtung]
Ein kritischer Hinweis.
:::
```

### YouTube-Embeds

YouTube-Videos kannst du direkt einbetten:

```markdown
https://www.youtube.com/watch?v=VIDEO_ID
```

### Relative Links

Verlinke zwischen Seiten mit relativen Pfaden:

```markdown
[Siehe auch: Blog Plugin](../plugins/blog.md)
```

Nexus löst die Links automatisch auf.

## Sync

Deine Dokumentation wird auf zwei Wegen synchronisiert:

- **Automatisch per Webhook** - Richte in GitHub einen Webhook ein der bei jedem Push Nexus benachrichtigt. So ist die Dokumentation immer aktuell.
- **Manuell** - Klicke in den Plugin-Einstellungen auf **Sync** um die Dokumentation manuell zu aktualisieren

:::tip[Tipp]
Richte den Webhook ein damit deine Doku automatisch aktuell bleibt. So musst du nach jeder Änderung im Repository nichts manuell anstoßen.
:::

## Base Path konfigurieren

Standardmäßig ist die Dokumentation unter `/guides/` erreichbar. Du kannst den Pfad anpassen:

1. Gehe zu **Einstellungen > Plugins > Guide**
2. Setze den **Base Path** (z.B. `/nexus/guide` statt `/guides/`)
3. Die Dokumentation ist sofort unter dem neuen Pfad erreichbar

Das ist nützlich wenn du mehrere Dokumentationen oder einen spezifischen URL-Aufbau brauchst.
