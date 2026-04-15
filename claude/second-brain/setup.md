---
title: Setup in 30 Minuten
order: 4
excerpt: Von Null zum fertigen Second Brain - zwei Wege, klarer Pfad
---

# Setup in 30 Minuten

Zwei Wege zum gleichen Ergebnis. Wähle den der zu dir passt.

## Voraussetzungen

- Du hast ein GitHub-Konto (kostenlos auf github.com)
- Du hast entweder **GitHub Desktop** installiert ODER **Claude Code** installiert
- Du hast einen Editor für Markdown (kann auch Claude Code selbst sein)

Wenn Git ein Fremdwort ist: zuerst [[git-basics|Git Grundlagen]] lesen.

## Weg A: Mit Claude Code (schnellster Weg)

TODO: Claude Code Skill `/init-brain` dokumentieren sobald gebaut.

Bis dahin: Template manuell clonen (siehe Weg B) und dann Claude Code im Ordner starten.

## Weg B: Mit GitHub Template

### Schritt 1: Template kopieren

1. Öffne `github.com/startandconnect/sac-brain-template`
2. Klicke **"Use this template"** oben rechts
3. Wähle einen Namen für dein Repo (z.B. `mein-brain`, `ben-wiki`)
4. Setze es auf **Private** (dein Wiki soll niemand sehen)
5. Klicke **"Create repository"**

Du hast jetzt ein eigenes Repo mit der Grundstruktur.

TODO: Screenshots Schritt für Schritt.

### Schritt 2: Lokal clonen

**GitHub Desktop:**
- File → Clone Repository → dein neues Repo auswählen → Ordner wählen → Clone

**Terminal:**
```bash
git clone https://github.com/DEIN-NAME/mein-brain.git
cd mein-brain
```

### Schritt 3: CLAUDE.md anpassen

Öffne `CLAUDE.md` und ersetze die Platzhalter:

- Wer du bist (Name, Rolle, Kontext)
- Was du hauptsächlich machst
- Welche Sprache (Deutsch/Englisch)
- Besondere Regeln

Das ist die erste Datei die Claude liest. Je klarer sie ist, desto besser die Antworten.

TODO: Vorlage mit Platzhaltern hier einbetten.

### Schritt 4: Erstes Projekt anlegen

Wähle ein echtes Projekt. Keine Übungsaufgabe.

```
projects/
└── dein-projekt/
    └── context.md
```

Kopiere die Vorlage aus dem Template und fülle sie mit echten Informationen.

### Schritt 5: Claude Code starten

Im Wiki-Ordner:

```bash
claude
```

Stelle die erste Frage mit Kontext:

> Schau dir meine CLAUDE.md und das Projekt XYZ an. Was sind die nächsten 3 Aufgaben für mich?

Wenn die Antwort spezifisch und brauchbar ist: dein Second Brain funktioniert.

### Schritt 6: Committen und pushen

Damit dein Setup gesichert ist:

**GitHub Desktop:** Summary "Initial Setup" → Commit → Push origin.

**Terminal:**
```bash
git add .
git commit -m "Initial setup"
git push
```

## Was jetzt

Du hast ein laufendes Second Brain. Jetzt geht es um Routine und Pflege.

- [[taegliche-nutzung|Tägliche Nutzung]] - wie du es im Alltag einsetzt
- [[claude-md-anleitung|CLAUDE.md richtig schreiben]] - für bessere Antworten
- [[template-erklaert|Template erklärt]] - was drin ist und warum

:::tip[Wichtig]
Die ersten drei Tage fühlt sich das Wiki nach Arbeit an. Das ist normal. Nach der ersten Woche hast du den Punkt überschritten wo es anfängt, dir Zeit zurückzugeben.
:::
