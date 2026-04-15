---
title: Git Grundlagen
order: 3
excerpt: Das Minimum an Git das du für dein Wiki brauchst - mit GitHub Desktop, alles grafisch
---

# Git Grundlagen

Dieser Abschnitt richtet sich an alle die mit Git noch nie gearbeitet haben. Du lernst hier nicht Git für Entwickler, sondern genau die 20 Prozent die du für dein Wiki brauchst.

## Was ist Git in drei Sätzen

Git speichert Versionen deiner Dateien. Du kannst jederzeit zu einem älteren Stand zurück. Mit GitHub (oder GitLab) kannst du deine Dateien zusätzlich in der Cloud sichern und von mehreren Geräten darauf zugreifen.

Für dein Wiki heißt das: nichts geht verloren, alles ist nachvollziehbar, Backup ist automatisch.

## Du brauchst: GitHub Desktop

GitHub Desktop ist eine grafische App. Du klickst auf Buttons, Git macht den Rest.

- Download: github.com/desktop
- Mac, Windows, Linux
- Reicht für 100 Prozent aller Wiki-Aufgaben

Das ist alles was du brauchst. Keine Programmiersprache, keine Vorkenntnisse.

## Die Begriffe die du kennen musst

- **Repository (Repo):** dein Wiki-Ordner mit Git-Historie
- **Commit:** ein gespeicherter Zwischenstand deiner Dateien
- **Push:** deine Commits auf GitHub hochladen
- **Pull:** Änderungen von GitHub zu dir runterladen
- **Clone:** ein bestehendes Repo kopieren (z.B. das Template)

Das reicht. Alles andere lernst du später wenn du es brauchst.

## Erstes Mal: GitHub Desktop einrichten

1. GitHub Desktop installieren (github.com/desktop)
2. App öffnen
3. Mit deinem GitHub-Konto einloggen (oder Konto neu erstellen wenn noch nicht vorhanden)
4. Im Setup-Dialog: dein Name und E-Mail (wird in deinen Commits gezeigt)

Fertig. Die App ist einsatzbereit.

## Repo runterladen (Clone)

Wenn du z.B. das Template clonen willst:

1. GitHub Desktop öffnen
2. **File → Clone Repository** anklicken
3. Tab "URL" wählen
4. Repo-URL eingeben (z.B. `https://github.com/startandconnect/sac-brain-template`)
5. Lokalen Ordner wählen (z.B. `~/Documents/`)
6. **Clone** klicken

Der Repo-Inhalt liegt jetzt auf deinem Rechner.

## Tägliche Nutzung: Änderungen sichern

Du hast Dateien in deinem Wiki geändert (mit Claude App, mit deinem Editor, egal). Jetzt willst du das sichern.

1. GitHub Desktop öffnen (falls nicht schon offen)
2. Im "Changes"-Tab siehst du alle geänderten Dateien
3. Im Feld "Summary" kurz beschreiben was sich geändert hat (z.B. "Tagesnotiz angelegt", "Projekt XYZ aktualisiert")
4. **"Commit to main"** klicken (unten links)
5. **"Push origin"** klicken (oben rechts)

Fertig. Sechs Klicks, deine Änderungen sind auf GitHub gesichert.

## Was wenn ich was kaputtgemacht habe

### Versehentlich gelöscht oder kaputt geschrieben (noch nicht committet)

In GitHub Desktop:

1. Rechtsklick auf die Datei in der Changes-Liste
2. **"Discard changes"** wählen
3. Bestätigen

Datei ist wieder im Stand vom letzten Commit.

### Schon committet, möchte zurück

Im Menü: **History → letzten Commit auswählen → Rechtsklick → "Revert this commit"**.

GitHub Desktop macht den Commit rückgängig (durch einen neuen Commit, nichts geht verloren).

## Wenn du an mehreren Geräten arbeitest

Beispiel: morgens am Desktop, nachmittags am Laptop.

**Vor der Arbeit am neuen Gerät:**

1. GitHub Desktop öffnen
2. **"Fetch origin"** klicken (oben)
3. Wenn Updates da sind: **"Pull origin"** klicken

Damit hast du die neuesten Änderungen vom anderen Gerät.

**Nach der Arbeit:**

Wie beschrieben commiten und pushen.

**Goldene Regel:** immer pullen bevor du anfängst, immer pushen wenn du fertig bist. Dann gibt es nie Konflikte.

## Was du NICHT brauchst

- **Branches:** dein Wiki ist kein Softwareprojekt. Alles passiert auf `main`.
- **Pull Requests:** brauchst du nur wenn mehrere Leute am selben Repo arbeiten.
- **Merge Conflicts:** entstehen nur wenn du parallel an verschiedenen Geräten arbeitest, ohne vorher zu pullen. Bei der Goldenen Regel oben: kommen sie nicht vor.
- **Rebase, Cherry-Pick, Stash:** vergiss dass es sie gibt bis du sie brauchst.

## Typische Probleme und Lösungen

### "Failed to push some refs"

Auf GitHub gibt es Änderungen die du noch nicht hast. Erst **"Pull origin"** klicken, dann nochmal pushen.

### "Authentication failed"

GitHub-Login ist abgelaufen. **GitHub Desktop → Preferences → Accounts** und neu einloggen.

### "There are conflicting changes"

Du hast lokal geändert, gleichzeitig wurde auf GitHub auch geändert. GitHub Desktop fragt dich was du tun willst.

In den meisten Fällen reicht: **"Open in editor"** klicken, die markierten Stellen anschauen, die richtige Version wählen, speichern, in GitHub Desktop committen.

Wenn du nicht weißt was zu tun ist: Claude App fragen. Beschreibe das Problem, Claude führt dich durch die Lösung.

### "Ich sehe Änderungen die ich nicht gemacht habe"

Wenn du an mehreren Geräten arbeitest oder Auto-Sync aktiv ist (siehe [[advanced|Advanced]]): kommt vor. Pullen, Änderungen prüfen, weitermachen.

## Sicherheits-Basics

- **Niemals API Keys oder Passwörter committen.** Falls passiert: Key sofort rotieren.
- **Repo auf Private setzen.** Wikis sind persönlich, niemand soll sie sehen.
- **Vor jedem Commit kurz prüfen** was sich geändert hat (siehst du in GitHub Desktop)

:::tip[Ehrlich]
Git ist initial verwirrend. Nach einer Woche täglicher Nutzung mit GitHub Desktop geht es automatisch. Nicht von schlechten ersten Tagen abschrecken lassen.
:::
