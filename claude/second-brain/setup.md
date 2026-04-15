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

## Weg A: Mit Claude Code

Wenn Claude Code installiert ist, ist das der schnellste Weg:

```bash
cd ~/Documents
claude
```

Dann in Claude Code:

> Lege mir ein Second Brain in diesem Ordner an. Nutze die SAC Brain Template Struktur als Basis. Frag mich nach: meinem Namen, meiner Rolle, dem Ordnernamen, ob ich ein erstes Beispielprojekt willst.

Claude Code stellt dir die Fragen, legt die Struktur an und committet sie. Anschließend pushst du das Repo zu GitHub (siehe Schritt 6 weiter unten).

Alternativ wenn der Skill `/init-brain` existiert: einfach diesen aufrufen. Der erledigt alle Schritte in einem.

## Weg B: Mit GitHub Template

### Schritt 1: Template kopieren

1. Öffne `github.com/startandconnect/sac-brain-template`
2. Klicke **"Use this template"** oben rechts (grüner Button)
3. Wähle einen Namen für dein Repo (z.B. `mein-brain`, `ben-wiki`)
4. Setze es auf **Private** (dein Wiki soll niemand sehen)
5. Klicke **"Create repository"**

Du hast jetzt ein eigenes Repo mit der Grundstruktur. GitHub leitet dich auf das neue Repo weiter.

### Schritt 2: Lokal clonen

**Mit GitHub Desktop:**
- File → Clone Repository → dein neues Repo auswählen → Ordner wählen → Clone

**Mit Terminal:**

```bash
cd ~/Documents
git clone https://github.com/DEIN-NAME/mein-brain.git
cd mein-brain
```

### Schritt 3: CLAUDE.md anpassen

Öffne `CLAUDE.md` mit deinem Editor (oder direkt mit Claude Code: `claude` im Ordner starten und sagen "öffne CLAUDE.md zur Bearbeitung").

Im Template steht eine Vorlage mit Platzhaltern:

```markdown
# Wer ich bin

[NAME], [ROLLE]. Ich arbeite an [HAUPTPROJEKT].

# Was dieses Wiki ist

Mein persönliches Second Brain.

# Sprache und Stil

- Deutsch, außer technische Begriffe
- Echte Umlaute verwenden
- Du-Form, kein "Sie"

# Regeln

- Erledigte Aufgaben sofort als [x] markieren
- Keine API Keys oder Kundendaten in Dateien
```

Ersetze die Platzhalter durch echte Informationen. Das ist die wichtigste Datei - je klarer sie ist, desto besser die Antworten von Claude.

Details: [[claude-md-anleitung|CLAUDE.md richtig schreiben]].

### Schritt 4: Erstes Projekt anlegen

Wähle ein echtes Projekt. Keine Übungsaufgabe.

Lege einen Ordner an:

```bash
mkdir -p projects/dein-projekt
```

Erstelle `projects/dein-projekt/context.md` und nutze die context.md aus dem Beispielprojekt im Template als Vorlage. Fülle echte Informationen ein:

- Worum geht es in einem Satz
- Aktueller Stand
- Drei nächste Aufgaben
- Eine Entscheidung die du letzte Woche getroffen hast

### Schritt 5: Claude Code starten und testen

Im Wiki-Ordner:

```bash
claude
```

Stelle die erste Frage mit Kontext:

> Schau dir meine CLAUDE.md und das Projekt in projects/dein-projekt/ an. Was sind die nächsten 3 Aufgaben für mich?

Wenn die Antwort spezifisch und brauchbar ist: dein Second Brain funktioniert. Wenn die Antwort generisch ist: deine CLAUDE.md oder context.md ist zu vage. Iteriere.

### Schritt 6: Committen und pushen

Damit dein Setup gesichert ist:

**Mit GitHub Desktop:**

1. Wechsle zu GitHub Desktop
2. Du siehst die geänderten Dateien im Changes-Tab
3. Im Summary-Feld eintippen: "Initial Setup"
4. **"Commit to main"** klicken
5. **"Push origin"** klicken

**Mit Terminal:**

```bash
git add .
git commit -m "Initial setup"
git push
```

Fertig. Dein Second Brain ist live.

## Was jetzt

Du hast ein laufendes Second Brain. Jetzt geht es um Routine und Pflege.

- [[taegliche-nutzung|Tägliche Nutzung]] - wie du es im Alltag einsetzt
- [[claude-md-anleitung|CLAUDE.md richtig schreiben]] - für bessere Antworten
- [[template-erklaert|Template erklärt]] - was drin ist und warum

## Häufige Stolpersteine

### "Claude Code findet meine CLAUDE.md nicht"

Stelle sicher dass du Claude Code im richtigen Ordner startest (`cd mein-brain` davor). Claude liest CLAUDE.md aus dem aktuellen Verzeichnis.

### "Mein Push wird abgewiesen mit Auth-Fehler"

GitHub-Login fehlt. Einmalig GitHub Desktop einrichten und einloggen, dann läuft auch das Terminal.

### "Ich habe die Beispieldateien aus dem Template versehentlich gelöscht"

Kein Problem - sie sind nur als Referenz gedacht. Wenn du sie zurückwillst: `git checkout HEAD~1 -- projects/beispiel-projekt/` (in der Annahme dass du noch keinen Commit gemacht hast).

### "Soll ich das alles jetzt schon nutzen?"

Mach den Setup-Schritt fertig, leg ein erstes Projekt an. Mehr nicht. Erweitere wenn du echten Bedarf siehst, nicht aus Theorie.

:::tip[Wichtig]
Die ersten drei Tage fühlt sich das Wiki nach Arbeit an. Das ist normal. Nach der ersten Woche hast du den Punkt überschritten wo es anfängt, dir Zeit zurückzugeben.
:::
