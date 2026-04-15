---
title: Projects und Artifacts
order: 4
excerpt: Wie du im Web-Chat über einzelne Chats hinaus arbeitest
---

# Projects und Artifacts

Der Web-Chat (claude.ai) kann mehr als nur Fragen beantworten. Projects und Artifacts machen aus dem Chat ein Arbeitsumfeld.

## Projects

Ein Project ist ein Ordner für zusammengehörige Chats. Du kannst Dateien, Anweisungen und Hintergrundwissen hinterlegen, die für alle Chats in diesem Project gelten.

### Schritt für Schritt: erstes Project anlegen

1. Auf claude.ai einloggen
2. In der Seitenleiste links auf **Projects** klicken
3. **Create Project** klicken
4. Namen geben (z.B. "Mein Buchprojekt")
5. Optional: Beschreibung, Custom Instructions
6. Optional: Dateien hochladen (PDFs, Markdown, Bilder)

Ab jetzt landen alle Chats die du innerhalb des Projects führst dort und teilen sich denselben Kontext (deine hochgeladenen Dateien, deine Custom Instructions).

### Wann ein neues Project sinnvoll ist

- Längere Themen über Wochen oder Monate (Buchprojekt, Firmen-Recherche, Kurs-Erstellung)
- Wenn du immer wieder dieselbe Hintergrund-Information brauchst (Style Guide, Briefing, Domain-Wissen)
- Wenn die Anzahl Chats zu einem Thema mehrstellig wird

### Wann nicht

- Einmalige Aufgaben (überflüssiger Overhead)
- Wenn die Custom Instructions sich ständig ändern (Project ist dann schlechter Ort dafür)
- Wenn du bessere Werkzeuge hast (Claude Code mit Workspace ist mächtiger)

## Artifacts

Artifacts sind Inhalte, die Claude in einem eigenen Fenster neben dem Chat erzeugt: Code, Dokumente, Diagramme. Du kannst sie bearbeiten, speichern und iterieren.

Sobald Claude was Längeres oder Strukturiertes generiert (mehr als ein paar Absätze, Code-Blöcke, Tabellen), erscheint das oft als Artifact rechts neben dem Chat.

### Beispiele für Artifacts

- Lange Texte (Blogartikel, Konzepte)
- Code-Snippets oder ganze Scripts
- HTML-Prototypen die du direkt im Browser sehen kannst
- Mermaid-Diagramme
- Strukturierte Tabellen oder Listen

### Wann Artifacts helfen

- Du willst etwas Längeres das nicht im Chat-Stream untergeht
- Du willst iterieren ohne dass die Zwischenstufen den Chat zumüllen
- Du willst das Ergebnis raus exportieren (Copy, Download)

### Wann Artifacts stören

- Bei kurzen Antworten ist es Overkill
- Wenn du eigentlich nur eine Frage hast und keine Datei
- Bei Konversationen die im Chat besser fließen

Du kannst in den App-Einstellungen oft konfigurieren wann Artifacts auftauchen sollen.

## Konkreter Workflow: Konzept-Entwicklung mit Project + Artifacts

Beispiel: du arbeitest an einem Workshop-Konzept.

### Schritt 1: Project anlegen

Project: "Workshop Vibe Coding für Uni Kiel"
Custom Instructions: "Ich plane einen 8h-Workshop für 14 Teams an der Uni Kiel. Zielgruppe: Forschende und Studierende ohne Programmiererfahrung. Ziel: am Ende des Tages haben alle einen funktionierenden Prototyp. Tonalität: konkret, hands-on, nicht akademisch."

Dateien hochladen: Briefing-PDF von der Uni, Beispiel-Workshops anderer Anbieter, deine Notizen.

### Schritt 2: Strukturieren

Im Project ein neuer Chat: "Schlag mir eine Tagesstruktur vor: 8 Stunden, 1h Mittagspause. Welche Blöcke, in welcher Reihenfolge, mit welchem Ziel pro Block?"

Claude generiert die Struktur als Artifact - Tabelle mit Uhrzeit, Block-Titel, Ziel, Format.

### Schritt 3: Vertiefen

Pro Block ein eigener Chat (immer noch im selben Project): "Block 3 ist 'Erste Prototyp-Iteration'. Wie würde der konkret ablaufen? Was brauchen die Teams, was machen sie selbst, was machen wir gemeinsam?"

Die Tagesstruktur ist als Datei im Project verfügbar - Claude kann sich darauf beziehen.

### Schritt 4: Material erstellen

Nochmal neuer Chat: "Wir brauchen ein Handout für die Teilnehmer. Eine Seite, A4. Was muss drauf?" Claude generiert als Artifact, du iterierst, exportierst.

### Schritt 5: Wochen später wieder reinkommen

In zwei Wochen sind die Detailfragen wieder relevant. Du öffnest das Project, der ganze Kontext ist da. Kein Neustart, kein Briefing.

## Project vs Claude Code App

Wann was?

| Situation | Empfehlung |
|---|---|
| Einmalige Aufgabe | Web-Chat ohne Project |
| Längeres Thema, hauptsächlich Text | Web-Project |
| Du willst eigene Dateien strukturiert pflegen | Claude Code App + Workspace |
| Du arbeitest mit Code | Claude Code App + Workspace |
| Maximaler Kontext und Auto-Pflege | Claude Code App mit Wiki |

Projects sind ein Mittelweg zwischen Web-Chat und Claude Code. Wenn du mit Markdown-Dateien arbeiten willst (Wiki-Stil): Claude Code App ist mächtiger. Wenn du in claude.ai bleiben willst: Projects sind der nächste Schritt.

:::tip[Vorsicht]
Projects im Web sind nicht privat im Sinne "nur auf meinem Rechner". Sie liegen bei Anthropic. Keine Geschäftsgeheimnisse, keine Kundendaten ohne entsprechenden Datenschutzrahmen.
:::
