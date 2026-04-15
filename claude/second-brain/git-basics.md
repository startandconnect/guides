---
title: Git Grundlagen
order: 3
excerpt: Das Minimum an Git das du für dein Wiki brauchst - ohne unnötige Tiefe
---

# Git Grundlagen

Dieser Abschnitt richtet sich an alle die mit Git noch nie gearbeitet haben. Du lernst hier nicht Git für Entwickler, sondern genau die 20 Prozent die du für dein Wiki brauchst.

## Was ist Git in drei Sätzen

Git speichert Versionen deiner Dateien. Du kannst jederzeit zu einem älteren Stand zurück. Mit GitHub (oder GitLab) kannst du deine Dateien zusätzlich in der Cloud sichern und von mehreren Geräten darauf zugreifen.

Für dein Wiki heißt das: nichts geht verloren, alles ist nachvollziehbar, Backup ist automatisch.

## Zwei Wege: App oder Terminal

Du musst dich für einen Weg entscheiden. Beide Wege funktionieren, du kannst jederzeit wechseln.

### Weg A: GitHub Desktop (empfohlen für Einsteiger)

Eine grafische App. Du klickst auf Buttons, Git macht den Rest.

- Download: github.com/desktop
- Mac, Windows, Linux
- Funktioniert auch ohne Terminal-Erfahrung
- Reicht für 95 Prozent aller Wiki-Aufgaben

TODO: Screenshots von GitHub Desktop mit Wiki-Workflow.

### Weg B: Terminal

Direkter, mächtiger, schneller wenn man es kann. Wenn du Claude Code sowieso im Terminal nutzt, wirst du das früher oder später wollen.

Beide Wege können parallel existieren. Claude Code selbst nutzt Terminal-Git.

## Die Begriffe die du kennen musst

- **Repository (Repo):** dein Wiki-Ordner mit Git-Historie
- **Commit:** ein gespeicherter Zwischenstand deiner Dateien
- **Push:** deine Commits auf GitHub hochladen
- **Pull:** Änderungen von GitHub zu dir runterladen
- **Clone:** ein bestehendes Repo kopieren (z.B. das Template)

Das reicht. Alles andere lernst du später wenn du es brauchst.

## Die 5 Befehle (Terminal-Version)

```bash
# Einmalig: das Template clonen
git clone https://github.com/startandconnect/sac-brain-template mein-wiki
cd mein-wiki

# Was hat sich geändert?
git status

# Neue oder geänderte Dateien vormerken
git add .

# Commit mit Nachricht
git commit -m "Projekt XYZ angelegt"

# Auf GitHub hochladen
git push
```

TODO: Jeden Befehl mit Erklärung was er tut, was vorher gelaufen sein muss.

## GitHub Desktop Workflow (die gleichen Schritte)

1. **File → Clone Repository** → Template-URL rein → Lokaler Ordner wählen
2. Im Wiki Dateien ändern (mit Claude Code oder deinem Editor)
3. GitHub Desktop öffnet sich, zeigt Änderungen
4. Summary (kurze Beschreibung) eintippen → "Commit to main"
5. "Push origin" klicken

Fertig.

TODO: Screenshots Schritt für Schritt.

## Was du NICHT brauchst

- **Branches:** dein Wiki ist kein Softwareprojekt. Alles passiert auf `main`.
- **Pull Requests:** die brauchst du nur wenn mehrere Leute am selben Repo arbeiten.
- **Merge Conflicts:** entstehen nur wenn du parallel an verschiedenen Geräten arbeitest - erstmal einfach nicht machen.
- **Rebase, Cherry-Pick, Stash:** vergiss dass es sie gibt bis du sie brauchst (meist: nie).

## Typische Probleme

### "Your branch is ahead of origin/main by X commits"
Du hast committet aber nicht gepusht. Einfach `git push` oder "Push origin" in GitHub Desktop.

### "Your branch is behind origin/main"
Auf GitHub gibt es Änderungen die du noch nicht hast. `git pull` oder "Pull origin".

### Ich habe was versehentlich gelöscht
Solange du nicht committet hast: `git checkout Dateiname` holt es zurück. In GitHub Desktop: Rechtsklick auf die Datei → "Discard changes".

TODO: Mehr typische Situationen.

## Weiterführend

Wenn du tiefer einsteigen willst: die offizielle Git-Doku (git-scm.com) ist solide. Für Claude-Code-Nutzung reicht aber was hier steht.

:::tip[Ehrlich]
Git ist initial verwirrend. Nach einer Woche täglicher Nutzung geht es automatisch. Nicht von schlechten ersten Tagen abschrecken lassen.
:::
