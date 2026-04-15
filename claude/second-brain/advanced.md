---
title: Advanced
order: 8
excerpt: Wenn die Basis sitzt - Auto-Sync, Skills, externe Integrationen, Multi-Device
---

# Advanced

Dieser Abschnitt ist erst relevant wenn dein Second Brain seit mindestens 4 Wochen läuft. Vorher nicht reinschauen - du wirst nur kompliziert wo einfach reicht.

## Auto-Sync zwischen Geräten

Wenn du an mehreren Rechnern arbeitest (Laptop, Desktop, Arbeit, privat), willst du nicht manuell pullen und pushen.

### Option A: Launchd (Mac)

Ein Job der alle 5 Minuten automatisch pullt und pusht.

Erstelle eine Datei `~/Library/LaunchAgents/com.user.brain-sync.plist`:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>Label</key>
    <string>com.user.brain-sync</string>
    <key>ProgramArguments</key>
    <array>
        <string>/bin/bash</string>
        <string>-c</string>
        <string>cd ~/Documents/mein-brain && git pull --rebase --autostash && git add -A && git diff --cached --quiet || (git commit -m "Auto-sync $(date +%Y-%m-%d_%H:%M)" && git push)</string>
    </array>
    <key>StartInterval</key>
    <integer>300</integer>
    <key>StandardOutPath</key>
    <string>/tmp/brain-sync.log</string>
    <key>StandardErrorPath</key>
    <string>/tmp/brain-sync.log</string>
</dict>
</plist>
```

Aktivieren:

```bash
launchctl load ~/Library/LaunchAgents/com.user.brain-sync.plist
```

Logs prüfen wenn was schiefläuft: `tail -f /tmp/brain-sync.log`.

### Option B: systemd Timer (Linux)

Datei `~/.config/systemd/user/brain-sync.service`:

```ini
[Unit]
Description=Brain Auto-Sync

[Service]
Type=oneshot
WorkingDirectory=%h/Documents/mein-brain
ExecStart=/bin/bash -c 'git pull --rebase --autostash && git add -A && (git diff --cached --quiet || (git commit -m "Auto-sync $(date +%%Y-%%m-%%d_%%H:%%M)" && git push))'
```

Datei `~/.config/systemd/user/brain-sync.timer`:

```ini
[Unit]
Description=Brain Auto-Sync alle 5 Minuten

[Timer]
OnBootSec=2min
OnUnitActiveSec=5min

[Install]
WantedBy=timers.target
```

Aktivieren:

```bash
systemctl --user enable brain-sync.timer
systemctl --user start brain-sync.timer
```

### Option C: Obsidian Git Plugin

Wenn du Obsidian als Editor nutzt, ist das Git-Plugin der einfachste Weg:

1. Obsidian → Settings → Community Plugins → "Obsidian Git" installieren
2. Plugin-Einstellungen: Auto-Pull alle 5 min, Auto-Commit alle 10 min, Auto-Push nach Commit
3. Funktioniert auch auf Mobile mit Obsidian Mobile

### Option D: GitHub Actions

Wenn du spezielle Checks willst (Linter, Spell-Check, Link-Checker), kannst du GitHub Actions nutzen. Aber: meistens overkill für ein Wiki. Erst wenn du echte Probleme hast.

### Welche Option

- **Mac Solo-Nutzer:** Launchd
- **Linux Solo-Nutzer:** systemd Timer
- **Du willst mobile dabei haben:** Obsidian Git Plugin
- **Du arbeitest im Team:** GitHub Actions für CI

## Skills für Wiederkehrendes

Claude Code Skills automatisieren Routine-Aufgaben im Wiki. Beispiele:

### Skill: /tagesstart

Erstellt automatisch das Daily-File und gibt Briefing.

`~/.claude/skills/tagesstart/SKILL.md`:

```markdown
---
description: Tagesstart - liest Wiki, legt daily-Datei an, gibt Briefing
---

Fuehre folgende Schritte aus:

1. Pruefe ob daily/$(date +%Y-%m-%d).md schon existiert.
   - Wenn ja: oeffne sie, zeige aktuellen Inhalt
   - Wenn nein: lege sie an mit dem Template aus daily/_template.md

2. Lies CLAUDE.md und scanne projects/*/context.md.

3. Gib mir einen knappen Lagebericht:
   - Anzahl aktive Projekte
   - Offene kritische Themen
   - Drei Prioritaeten fuer heute basierend auf Status und Deadlines

4. Frage mich ob ich die drei Prios in die heutige daily-Datei
   uebernehmen will. Wenn ja: schreibe sie rein.
```

Aufruf in Claude Code: `/tagesstart`

### Skill: /projekt-init

Legt neuen Projektordner mit context.md-Template an.

`~/.claude/skills/projekt-init/SKILL.md`:

```markdown
---
description: Legt neuen Projekt-Ordner mit context.md an
arguments:
  name: Projekt-Name (slug, mit Bindestrichen)
  typ: kunde, eigenes-projekt, lernprojekt
---

1. Lege Ordner projects/{{name}}/ an.

2. Kopiere projects/_template/context.md nach projects/{{name}}/context.md.

3. Frage mich nach: kurzer Beschreibung, Status, Hauptziel, drei
   ersten offenen Aufgaben.

4. Fuelle die context.md mit den Antworten aus.

5. Zeige mir das Ergebnis und frage ob ich committen will.
```

Aufruf: `/projekt-init mein-neues-projekt eigenes-projekt`

### Skill: /wochenabschluss

Konsolidiert die Woche.

```markdown
---
description: Freitag-Rueckblick - Woche zusammenfassen, in Projekte uebertragen
---

1. Lies alle daily-Dateien dieser Woche (Montag bis Freitag).

2. Pro betroffenes Projekt:
   - Welche Aufgaben wurden erledigt
   - Welche neuen Themen sind aufgetaucht
   - Welche Entscheidungen wurden getroffen

3. Schlage mir vor was in welche context.md uebertragen werden soll.

4. Nach meinem OK: trage es ein, hake erledigte Todos ab.

5. Pruefe inbox.md und schlage Einsortierung vor.
```

Details zum Bau eigener Skills: [[../claude-code/skills-hooks-subagents|Skills, Hooks und Subagents]].

## Hooks für Disziplin

Ein Hook der bei jedem Session-Ende eine Erinnerung gibt:

`~/.claude/settings.json`:

```json
{
  "hooks": {
    "PostToolUse": [
      {
        "matcher": "Bash",
        "command": "echo 'Erinnerung: context.md aktuell halten' && grep -l 'TODO' projects/*/context.md 2>/dev/null | head -3"
      }
    ]
  }
}
```

Einer der vor jedem Push prüft ob CLAUDE.md aktuell ist (Beispiel als Pre-Push-Hook im Repo `.git/hooks/pre-push`):

```bash
#!/bin/bash
last_modified=$(git log -1 --format=%ct CLAUDE.md)
now=$(date +%s)
days=$(( (now - last_modified) / 86400 ))
if [ $days -gt 90 ]; then
    echo "Warnung: CLAUDE.md wurde seit $days Tagen nicht angepasst."
    echo "Schau ob alles noch aktuell ist."
fi
```

## MCP Server für Wiki-Integration

Wenn du einen MCP Server baust der dein Wiki versteht (Suche, Tags, Graph), bekommt Claude Code einen strukturierten Zugang zu deinem Wissen - nicht nur "lies Datei X" sondern "finde alle Notizen zu Thema Y".

Konkrete Use-Cases:

- **Volltextsuche:** "finde alle Stellen wo ich Stripe erwähnt habe" - schneller als grep
- **Tag-System:** Notizen mit `#topic` taggen und MCP gibt Liste pro Tag
- **Graph-Abfragen:** "welche Projekte hängen mit Kunde X zusammen"
- **Auto-Linking:** Wikilinks (`[[name]]`) automatisch auflösen

Warnung: eher ein Wochenende-Projekt, kein Must-Have. Für 99 Prozent der Fälle reicht Claude Code mit normaler Datei-Lese-Fähigkeit.

Wer sich rantraut: Anthropic MCP Spec lesen (modelcontextprotocol.io), TypeScript- oder Python-SDK nutzen.

## Externe Integrationen

### Notion / Obsidian als zusätzlicher Viewer

Wenn du visuell lesen willst, kannst du deinen Wiki-Ordner als Notion-Import nutzen oder in Obsidian öffnen. Die Markdown-Dateien funktionieren in beiden. Obsidian ist stärker weil es direkt mit dem Ordner arbeitet, ohne Import.

Setup Obsidian:

1. Obsidian installieren
2. "Open folder as vault" → deinen Wiki-Ordner wählen
3. Fertig - du kannst jetzt parallel mit Claude Code (im Terminal) und Obsidian (visuell) arbeiten

### Kalender-Anbindung

Für Morning Routine: Calendar-API fragen, Termine in daily-Datei einfügen. Als Skill oder Shortcut.

Beispiel-Skill `/morning-with-calendar`:

```markdown
---
description: Morning-Briefing inkl. Kalender-Termine
---

1. Hole heutige Kalender-Termine via gcal CLI:
   `gcal --start-date today --end-date today`

2. Lies CLAUDE.md und Projekt-contexts.

3. Erstelle daily-Datei mit:
   - Terminen aus Kalender
   - Drei Prios basierend auf Projekten
   - Geblockte Zeiten ausweisen

4. Wenn ein Termin fuer ein bestimmtes Projekt ist: erwaehne den
   Stand des Projekts (aus context.md).
```

### Newsletter / Blog aus dem Wiki speisen

Inhalte aus reference/ oder projects/ als Quellmaterial für Blog-Posts nutzen. Claude Code liest Wiki, schreibt Entwurf, du finalisierst.

Konkreter Workflow:

1. Im Wiki: alle Sessions/Notes der letzten zwei Wochen zu einem Thema durchschauen
2. Claude bitten: "Mach daraus einen Blogartikel-Entwurf in unserem Stil. Beispiele für Stil: blog/2026-04-01.md, blog/2026-03-15.md."
3. Entwurf in `content/draft-YYYY-MM-DD.md` ablegen
4. Manuelles Editing, finalisieren
5. Veröffentlichen, in `content/published/` verschieben

Spart Stunden bei jedem Artikel.

### Email-Drafts aus Wiki

Beispiel: Mail an Kunden zum Projektstand.

```
Schau in projects/kunde-xyz/context.md, was wir besprochen haben
und in den letzten daily-Dateien, was sich getan hat.

Schreibe einen Status-Update als E-Mail an Max Mustermann.
Tonalitaet: freundlich, professionell, konkret. Keine Floskeln.
Ende mit nachster sinnvoller Frage an ihn.
```

## Multi-User Wikis (Teams)

Möglich, aber mit Fallstricken:

- Pro Person eigener Branch? Meist zu viel Overhead.
- Einfacher: ein gemeinsames main, klarer Ownership pro Ordner/Datei.
- Konventionen müssen glasklar sein, sonst entsteht Chaos (zwei Leute legen unabhängig `kunde-x/` an mit verschiedener Schreibweise).
- Sensibles ist im Team-Wiki schwierig (private Notizen, Halb-Gedanken).

Für Teams ab 3 Personen würde ich ein dediziertes Wiki-Tool (Outline, BookStack, Confluence) in Betracht ziehen statt Markdown-Repo. Das Team-Wiki dort, persönliches Second Brain trotzdem als eigenes Markdown-Repo.

## Was du dir nicht antun solltest

- **Zu viele Plugins installieren.** Je mehr Tooling, desto mehr Wartung.
- **Perfekte Strukturen in der Theorie entwerfen.** Aus Use-Cases wachsen, nicht aus Diagrammen.
- **Dein Wiki als Content-Maschine missbrauchen.** Es ist Second Brain, nicht Blogsoftware.
- **Multi-User-Setups erzwingen.** Wenn dein Team kein Markdown-Repo will, kann nur dein eigenes Brain Markdown sein.

:::tip[Meta]
Alles hier ist optional. Dein Second Brain ist dann am wertvollsten, wenn du es wirklich nutzt - nicht wenn es am meisten Features hat.
:::
