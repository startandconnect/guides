---
title: Setup in 30 Minuten
order: 4
excerpt: Von Null zum fertigen Second Brain - mit Claude App und GitHub Desktop
---

# Setup in 30 Minuten

Du brauchst zwei Apps: die Claude App und GitHub Desktop. Beide kostenlos, beide grafisch.

## Voraussetzungen

- Du hast ein GitHub-Konto (kostenlos auf github.com)
- Du hast die **Claude App** installiert (siehe [[../claude-code/installation|Installation]])
- Du hast **GitHub Desktop** installiert (download.github.com)

Wenn Git ein Fremdwort ist: zuerst [[git-basics|Git Grundlagen]] lesen.

## Schritt 1: Template auf GitHub kopieren

1. Öffne `github.com/startandconnect/sac-brain-template` in deinem Browser
2. Klicke **"Use this template"** oben rechts (grüner Button)
3. Wähle einen Namen für dein Repo (z.B. `mein-brain`, `vorname-wiki`)
4. Setze es auf **Private** (dein Wiki soll niemand sehen)
5. Klicke **"Create repository"**

Du hast jetzt ein eigenes Repo mit der Grundstruktur. GitHub leitet dich auf das neue Repo weiter.

## Schritt 2: Repo mit GitHub Desktop runterladen

1. GitHub Desktop öffnen
2. **File → Clone Repository** anklicken
3. In der Liste dein neues Repo auswählen (oder URL einfügen)
4. Lokalen Ordner wählen (z.B. `~/Documents/mein-brain`)
5. **Clone** klicken

Der Ordner ist jetzt auf deinem Rechner.

## Schritt 3: Ordner in der Claude App verbinden

1. Claude App öffnen
2. Auf **Workspace verbinden** klicken (oder das Ordner-Symbol)
3. Den eben erstellten Wiki-Ordner auswählen
4. Berechtigung bestätigen

Claude kann jetzt Dateien in deinem Wiki lesen und schreiben.

## Schritt 4: CLAUDE.md anpassen

In der Claude App fragen:

```
Oeffne CLAUDE.md im Workspace und zeige mir den aktuellen Inhalt.
```

Claude zeigt dir die Vorlage. Dann:

```
Pass die CLAUDE.md an meine Situation an. Stell mir Fragen die du
brauchst (Name, Rolle, was ich mache, Sprache, Stil-Praeferenzen)
und ueberschreib dann die Datei.
```

Claude führt dich durch die Fragen und passt die Datei an.

## Schritt 5: Erstes Projekt anlegen

Wähle ein echtes Projekt. Keine Übungsaufgabe.

In der Claude App:

```
Lege ein neues Projekt an: projects/[PROJEKTNAME]/context.md.
Nutze die Vorlage aus dem Template als Basis.

Frag mich nach: kurze Beschreibung, Status, Hauptziel, drei
ersten Aufgaben.
```

Claude legt den Ordner und die Datei an, fragt dich die Details, fertigt die context.md.

## Schritt 6: Testen ob es funktioniert

In der Claude App:

```
Schau dir meine CLAUDE.md und das Projekt in projects/[PROJEKTNAME]/
an. Was sind die naechsten 3 Aufgaben fuer mich?
```

Wenn die Antwort spezifisch und brauchbar ist: dein Second Brain funktioniert.

Wenn die Antwort generisch ist: deine CLAUDE.md oder context.md ist zu vage. Ergänze konkrete Informationen, frag nochmal.

## Schritt 7: Erste Sicherung mit GitHub Desktop

Damit dein Setup gesichert ist:

1. Wechsle zu GitHub Desktop
2. Du siehst die geänderten Dateien im "Changes"-Tab
3. Im Summary-Feld eingeben: "Initial Setup"
4. **"Commit to main"** klicken (unten links)
5. **"Push origin"** klicken (oben rechts) - Änderungen sind jetzt auf GitHub gesichert

Fertig. Dein Second Brain ist live und gesichert.

## Was jetzt

Du hast ein laufendes Second Brain. Jetzt geht es um Routine und Pflege.

- [[taegliche-nutzung|Tägliche Nutzung]] - wie du es im Alltag einsetzt
- [[claude-md-anleitung|CLAUDE.md richtig schreiben]] - für noch bessere Antworten
- [[template-erklaert|Template erklärt]] - was im Template steckt und wie du anpasst

## Häufige Stolpersteine

### "Claude Code findet meine CLAUDE.md nicht"

Stell sicher dass der richtige Workspace verbunden ist. In der App: oben den Workspace prüfen. Wenn nötig: anderen Workspace auswählen oder neu verbinden.

### "GitHub Desktop fragt nach Login"

Beim ersten Start einmalig mit deinem GitHub-Konto einloggen. Danach merkt sich GitHub Desktop die Credentials.

### "Push wird abgewiesen"

Meist GitHub-Login-Problem. Im Menü "GitHub Desktop → Preferences → Accounts" prüfen ob du eingeloggt bist.

### "Ich habe die Beispieldateien aus dem Template versehentlich gelöscht"

Kein Problem. In GitHub Desktop: Rechtsklick auf die gelöschte Datei → "Discard changes". Datei ist wieder da.

### "Soll ich das alles jetzt schon nutzen?"

Mach den Setup-Schritt fertig, leg ein erstes Projekt an. Mehr nicht. Erweitere wenn du echten Bedarf siehst, nicht aus Theorie.

:::tip[Wichtig]
Die ersten drei Tage fühlt sich das Wiki nach Arbeit an. Das ist normal. Nach der ersten Woche hast du den Punkt überschritten wo es anfängt, dir Zeit zurückzugeben.
:::
