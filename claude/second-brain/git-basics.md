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
git clone https://github.com/startandconnect/sac-brain-template mein-brain
cd mein-brain
```

`git clone <url> <ordner>` lädt das Template runter und legt es in einen lokalen Ordner. Du brauchst das nur einmal pro Repo.

```bash
# Was hat sich geändert?
git status
```

`git status` zeigt dir welche Dateien neu oder geändert sind. Sicher und unschädlich - du kannst es so oft ausführen wie du willst.

```bash
# Neue oder geänderte Dateien vormerken
git add .
```

`git add .` markiert alle Änderungen für den nächsten Commit. Der Punkt heißt "alles im aktuellen Ordner". Statt `.` kannst du auch konkrete Dateinamen angeben.

```bash
# Commit mit Nachricht
git commit -m "Projekt XYZ angelegt"
```

`git commit` packt die markierten Änderungen in einen Versionsstand. Die Nachricht in `-m "..."` beschreibt was du gemacht hast - dein zukünftiges Ich wird sich freuen.

```bash
# Auf GitHub hochladen
git push
```

`git push` schiebt deine Commits zu GitHub. Damit ist dein Stand gesichert und auf anderen Geräten verfügbar.

## GitHub Desktop Workflow (die gleichen Schritte)

1. **File → Clone Repository** → Template-URL eingeben → lokalen Ordner wählen → Clone klicken
2. Im Wiki Dateien ändern (mit Claude Code oder deinem Editor)
3. GitHub Desktop wechselt automatisch in den "Changes"-Tab und zeigt was sich geändert hat
4. Im Feld "Summary" eine kurze Beschreibung tippen (z.B. "Tagesnotiz angelegt")
5. **"Commit to main"** klicken (unten links)
6. **"Push origin"** klicken (oben rechts) - Änderungen sind jetzt auf GitHub

Fertig. Diese sechs Schritte deckst du täglich ab.

## Was du NICHT brauchst

- **Branches:** dein Wiki ist kein Softwareprojekt. Alles passiert auf `main`.
- **Pull Requests:** die brauchst du nur wenn mehrere Leute am selben Repo arbeiten.
- **Merge Conflicts:** entstehen nur wenn du parallel an verschiedenen Geräten arbeitest - erstmal einfach nicht machen.
- **Rebase, Cherry-Pick, Stash:** vergiss dass es sie gibt bis du sie brauchst (meist: nie).

## Typische Probleme

### "Your branch is ahead of origin/main by X commits"

Du hast committet aber nicht gepusht. Einfach `git push` oder "Push origin" in GitHub Desktop. Kein Drama.

### "Your branch is behind origin/main"

Auf GitHub gibt es Änderungen die du noch nicht hast. `git pull` oder "Pull origin". Passiert wenn du an mehreren Geräten arbeitest.

### "Your branch and origin/main have diverged"

Du hast lokal commits, auf GitHub gibt es auch neue commits, die zueinander passen müssen. `git pull --rebase` löst das in 90 Prozent der Fälle. In GitHub Desktop: "Pull" klicken, App fragt dich was sie tun soll.

### Ich habe was versehentlich gelöscht

Solange du nicht committet hast: `git checkout -- Dateiname` holt es zurück. In GitHub Desktop: Rechtsklick auf die Datei → "Discard changes". Falls du schon committet hast: `git revert HEAD` macht den letzten Commit rückgängig (ohne Datenverlust).

### "Permission denied (publickey)"

Dein GitHub-Zugang ist nicht eingerichtet. Lösung: GitHub Desktop installieren und einmalig damit einloggen, dann nutzt auch das Terminal die Credentials. Oder SSH-Key bei GitHub hinterlegen (offizielle Anleitung im GitHub-Help).

### Mein Push wird abgewiesen

Meist weil jemand (oder du an einem anderen Gerät) etwas anderes gepusht hat. Erst `git pull` oder `git pull --rebase`, dann nochmal `git push`.

## Sicherheits-Basics

- **Niemals API Keys oder Passwörter committen.** Falls passiert: Key sofort rotieren, History bereinigen.
- **`.gitignore` nutzen.** Datei im Repo-Root die festlegt was Git ignorieren soll. Im Template ist eine vorbereitete Version drin.
- **Repo auf Private setzen.** Wikis sind persönlich, niemand soll sie sehen.

## Weiterführend

Wenn du tiefer einsteigen willst: die offizielle Git-Doku (git-scm.com) ist solide. Für Claude-Code-Nutzung reicht aber was hier steht.

:::tip[Ehrlich]
Git ist initial verwirrend. Nach einer Woche täglicher Nutzung geht es automatisch. Nicht von schlechten ersten Tagen abschrecken lassen.
:::
