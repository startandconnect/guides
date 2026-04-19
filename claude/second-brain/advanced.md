---
title: Advanced
order: 8
excerpt: Wenn die Basis sitzt - Auto-Sync, Skills, Connectors, Multi-Device
---

# Advanced

Dieser Abschnitt ist erst relevant wenn dein Second Brain seit mindestens 4 Wochen läuft. Vorher nicht reinschauen - du wirst nur kompliziert wo einfach reicht.

Manche Inhalte hier sind technischer und richten sich an erfahrene Nutzer. Wenn etwas zu tief geht, überspring es einfach.

## Auto-Sync zwischen Geräten

Wenn du an mehreren Rechnern arbeitest (Laptop, Desktop), willst du nicht manuell pullen und pushen.

### Option A: Obsidian Git Plugin (am einfachsten)

Wenn du Obsidian als zusätzlichen Editor nutzt:

1. Obsidian → Settings → Community Plugins → "Obsidian Git" installieren
2. Plugin-Einstellungen: Auto-Pull alle 5 Minuten, Auto-Commit alle 10 Minuten, Auto-Push nach Commit
3. Funktioniert auch auf Mobile mit Obsidian Mobile

Diese Option ist die empfohlene Variante für die meisten.

### Option B: GitHub Desktop manuell, aber öfter

Wenn du nur einen Rechner hast oder bewusst Kontrolle willst:

- Nach jeder Session: GitHub Desktop öffnen, committen, pushen (Routine)
- Vor dem Wechsel auf ein anderes Gerät: pushen
- Auf dem anderen Gerät: erst pullen, dann arbeiten

Funktioniert, ist aber Disziplin-Sache.

## Skills für wiederkehrende Aufgaben

Skills automatisieren Routinen in der Claude App. Statt jedes Mal denselben Prompt zu tippen, definierst du den Skill einmal und rufst ihn ab.

### Skill: Tagesstart

In der Claude App unter Einstellungen einen Skill anlegen:

- Name: `tagesstart`
- Trigger: wenn du `/tagesstart` schreibst
- Anweisung:

```
Fuehre folgende Schritte aus:

1. Pruefe ob sessions/[heutiges Datum].md schon existiert.
   - Wenn ja: oeffne sie, zeige aktuellen Inhalt.
   - Wenn nein: lege sie an mit dem Template aus sessions/_template.md

2. Lies CLAUDE.md und scanne projects/*/context.md.

3. Gib mir einen knappen Lagebericht:
   - Anzahl aktive Projekte
   - Offene kritische Themen
   - Drei Prioritaeten fuer heute basierend auf Status und Deadlines

4. Frage mich ob ich die drei Prios in die heutige sessions-Datei
   uebernehmen will. Wenn ja: schreibe sie rein.
```

Aufruf in der App: `/tagesstart` - fertig.

### Skill: Projekt-Init

Legt automatisch einen neuen Projektordner an.

- Name: `projekt-init`
- Anweisung:

```
1. Frag mich nach Projekt-Name (slug, mit Bindestrichen) und Typ
   (Kunde / Eigenes Projekt / Lernprojekt).

2. Lege Ordner projects/[name]/ an.

3. Kopiere projects/_template/context.md nach projects/[name]/context.md.

4. Frage mich nach: kurzer Beschreibung, Status, Hauptziel, drei
   ersten offenen Aufgaben.

5. Fuelle die context.md mit den Antworten aus.

6. Zeige mir das Ergebnis und frage ob ich es so passt.
```

### Skill: Wochenabschluss

Konsolidiert die Woche.

- Name: `wochenabschluss`
- Anweisung:

```
1. Lies alle sessions-Dateien dieser Woche (Montag bis Freitag).

2. Pro betroffenes Projekt:
   - Welche Aufgaben wurden erledigt
   - Welche neuen Themen sind aufgetaucht
   - Welche Entscheidungen wurden getroffen

3. Schlage mir vor was in welche context.md uebertragen werden soll.

4. Nach meinem OK: trage es ein, hake erledigte Todos ab.

5. Pruefe INBOX.md und schlage Einsortierung vor.
```

Mehr zu Skills im Detail: [[../claude-code/skills-hooks-subagents|Skills, Hooks und Subagents]].

## Connectors für externe Tools

Wenn dein Second Brain mit anderen Tools spricht, sparst du dir noch mehr manuelle Arbeit.

### Notion-Connector

Wenn du parallel Notion nutzt (z.B. für Team-Wissen während Wiki dein persönliches Brain ist):

> Suche in meinem Notion nach Notizen zum Thema X und ergaenze die
> wichtigsten Erkenntnisse in reference/x.md im Wiki.

### Kalender-Connector

Für Morning Routine mit Terminen:

> Hole heutige Kalender-Termine. Lege sessions/[heutiges Datum].md an
> mit den Terminen plus drei Prioritaeten aus dem Wiki.

### Email-Drafts mit Wiki-Kontext

> Schau in projects/kunde-x/context.md was wir besprochen haben und
> in den letzten sessions-Dateien was sich getan hat.
>
> Schreibe einen Status-Update als E-Mail an Max Mustermann.
> Tonalitaet: freundlich, professionell, konkret. Keine Floskeln.
> Ende mit naechster sinnvoller Frage an ihn.

Mehr zu Connectors: [[../claude-code/mcp-server|MCP Server und Connectors]].

## Newsletter / Blog aus dem Wiki

Inhalte aus reference/ oder projects/ als Quellmaterial für Blog-Posts nutzen.

Konkreter Workflow in der Claude App:

> Ich will einen Blogartikel schreiben zum Thema [THEMA].
> Schau in reference/ und in den letzten 2 Wochen sessions/ ob ich
> dazu Material habe.
>
> Wenn ja: mach daraus einen Artikel-Entwurf in unserem Stil.
> Beispiele für Stil: blog/2026-04-01.md, blog/2026-03-15.md.
> Speichere als content/draft-[heute].md.

Du finalisierst manuell, veröffentlichst, verschiebst nach `content/published/`.

Spart Stunden bei jedem Artikel.

## Multi-User Wikis (Teams)

Möglich, aber mit Fallstricken:

- Pro Person eigener Branch? Meist zu viel Overhead.
- Einfacher: ein gemeinsames `main`, klarer Ownership pro Ordner/Datei.
- Konventionen müssen glasklar sein, sonst entsteht Chaos (zwei Leute legen unabhängig `kunde-x/` an mit verschiedener Schreibweise).
- Sensibles ist im Team-Wiki schwierig (private Notizen, Halb-Gedanken).

Für Teams ab 3 Personen würde ich ein dediziertes Wiki-Tool (Outline, BookStack, Confluence) in Betracht ziehen statt Markdown-Repo. Das Team-Wiki dort, persönliches Second Brain trotzdem als eigenes Markdown-Repo.

## Mobile-Setup ausbauen

Für ernsthafte Mobile-Nutzung:

### iOS

- **Working Copy** (kostenpflichtig, aber sehr gut) als Git-Client
- **1Writer** oder **iA Writer** als Markdown-Editor
- Beide sind in Working Copy integrierbar
- Dadurch: lesen, schreiben, committen, pushen auf dem iPhone/iPad

### Android

- **Markor** (kostenlos) als Editor mit Git-Support
- Oder **Obsidian Mobile** mit Git-Plugin
- Funktioniert ähnlich gut wie Desktop

### Allgemein

GitHub Web-UI funktioniert auch auf dem Handy gut für Quick-Edits an `INBOX.md`. Reicht für die meisten Mobile-Use-Cases.

## Was du dir nicht antun solltest

- **Zu viele Plugins und Skills installieren.** Je mehr Tooling, desto mehr Wartung.
- **Perfekte Strukturen in der Theorie entwerfen.** Aus Use-Cases wachsen, nicht aus Diagrammen.
- **Dein Wiki als Content-Maschine missbrauchen.** Es ist Second Brain, nicht Blogsoftware.
- **Multi-User-Setups erzwingen.** Wenn dein Team kein Markdown-Repo will, kann nur dein eigenes Brain Markdown sein.

:::tip[Meta]
Alles hier ist optional. Dein Second Brain ist dann am wertvollsten, wenn du es wirklich nutzt - nicht wenn es am meisten Features hat.
:::
