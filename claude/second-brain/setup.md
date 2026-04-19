---
title: Setup in 10 Minuten
order: 4
excerpt: Von Null zum fertigen Second Brain - ZIP herunterladen, entpacken, mit Claude einrichten
---

# Setup in 10 Minuten

Du brauchst eine App: die Claude Desktop App. Optional plus Obsidian als grafischer Editor. Kein Git, kein Terminal.

## Voraussetzungen

- Du hast die **Claude Desktop App** installiert (claude.ai/download, siehe [[../claude-code/installation|Installation]])
- Optional: **Obsidian** als Editor (obsidian.md)

## Der schnellste Weg: Template herunterladen

Das Second Brain Template ist eine fertige Ordnerstruktur mit allen wichtigen Dateien. Du packst sie aus, verbindest sie mit Claude und das Wiki ist einsatzbereit.

:::tip[Template jetzt laden]
[Second Brain Template herunterladen (ZIP, 30 KB)](https://startandconnect.com/api/media-library/files/cmo6dm9fg00ax4bmwgf9r83t1/second-brain-template.zip)
:::

### Schritt 1: ZIP entpacken

1. Lade die ZIP-Datei herunter
2. Entpacke sie an einen festen Platz auf deinem Rechner (z.B. `~/Documents/mein-brain`)
3. Den Ordner-Namen kannst du frei wählen - "mein-brain", "vorname-wiki", was immer du willst

### Schritt 2: Ordner in der Claude App verbinden

1. Claude App öffnen
2. Auf **Workspace verbinden** klicken (oder das Ordner-Symbol)
3. Den eben entpackten Ordner auswählen
4. Berechtigung bestätigen

Claude kann jetzt Dateien in deinem Wiki lesen und schreiben.

### Schritt 3: Optional - Obsidian als Editor öffnen

Wenn du visuell in deinem Wiki herumklicken willst:

1. Obsidian öffnen
2. "Open folder as vault" wählen
3. Gleichen Ordner wie in der Claude App auswählen

Ab jetzt kannst du zwischen Claude App (Chat + Datei-Bearbeitung) und Obsidian (grafischer Editor) wechseln - beide lesen und schreiben die gleichen Dateien.

### Schritt 4: Onboarding mit Claude durchlaufen

Das Template enthält eine `SETUP.md` Datei. Die ist die Anleitung für Claude, wie dein Wiki an dich angepasst wird.

In der Claude App fragen:

```
Lies SETUP.md und führe das Onboarding durch.
```

Claude fragt dich ein paar Dinge:

- Welcher Typ bist du: Studierende, Angestellte oder Selbstständig?
- Wie heisst du, was machst du?
- Deutsch oder Englisch, Du oder Sie?
- Willst du ein erstes Projekt anlegen?

Claude füllt dann die `CLAUDE.md` aus, löscht die nicht passenden Beispielprojekte und fragt ob du direkt ein echtes Projekt anlegen willst.

### Schritt 5: Testen

In der Claude App fragen:

```
Schau dir meine CLAUDE.md und meine Projekte an. Was sind die nächsten
drei Aufgaben für mich?
```

Wenn die Antwort spezifisch und brauchbar ist: dein Second Brain funktioniert. Wenn die Antwort generisch ist: deine CLAUDE.md oder context.md ist zu vage. Mehr Infos reinschreiben und nochmal fragen.

## Was jetzt

Du hast ein laufendes Second Brain. Jetzt geht es um Routine und Pflege.

- [[taegliche-nutzung|Tägliche Nutzung]] - wie du es im Alltag einsetzt
- [[claude-md-anleitung|CLAUDE.md richtig schreiben]] - für noch bessere Antworten
- [[template-erklaert|Template erklärt]] - was im Template steckt und wie du anpasst

## Optional später: Git und Sync

Wenn du dein Wiki auf mehreren Geräten nutzen oder sichern willst, kannst du es zu einem Git-Repo machen. Details in [[git-basics|Git Grundlagen]]. Kein Muss - dein Wiki funktioniert auch rein lokal.

## Häufige Stolpersteine

### "Claude Code findet meine CLAUDE.md nicht"

Stell sicher dass der richtige Workspace verbunden ist. In der App: oben den Workspace prüfen. Wenn nötig: anderen Workspace auswählen oder neu verbinden.

### "Das Onboarding startet nicht"

Prüfe ob die Datei `SETUP.md` tatsächlich im Workspace liegt und die `CLAUDE.md` noch Platzhalter in eckigen Klammern enthält (z.B. `[DEIN NAME]`). Nur dann startet Claude das Onboarding.

### "Ich habe die Beispieldateien versehentlich gelöscht"

Kein Problem. Lade die ZIP nochmal runter und kopiere die fehlenden Dateien. Oder bitte Claude: *"Lies das Template nochmal aus der ZIP und füge die fehlenden Strukturen wieder ein."*

### "Soll ich das alles jetzt schon nutzen?"

Mach den Setup-Schritt fertig, leg ein erstes Projekt an. Mehr nicht. Erweitere wenn du echten Bedarf siehst, nicht aus Theorie.

:::tip[Wichtig]
Die ersten drei Tage fühlt sich das Wiki nach Arbeit an. Das ist normal. Nach der ersten Woche hast du den Punkt überschritten wo es anfängt, dir Zeit zurückzugeben.
:::
