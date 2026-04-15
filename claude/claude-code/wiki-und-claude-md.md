---
title: Wiki und CLAUDE.md
order: 5
excerpt: Die wichtigste Angewohnheit - Kontext permanent verfügbar machen
---

# Wiki und CLAUDE.md

Wenn du Claude Code ernsthaft nutzen willst, brauchst du einen Ort an dem dein Kontext lebt. Dieser Ort ist ein Wiki plus eine CLAUDE.md Datei.

## Was ist CLAUDE.md

Eine Markdown-Datei die Claude Code automatisch liest, wenn du mit dem Ordner arbeitest. Dort steht alles was Claude wissen muss: wer du bist, woran du arbeitest, welche Regeln gelten.

Sie liegt einfach im Hauptordner deines Workspaces (z.B. dein Wiki-Ordner). Claude erkennt sie automatisch und nutzt sie als Grundkontext für jeden Chat in diesem Workspace.

## Warum eine einzige Datei einen so großen Unterschied macht

**Ohne CLAUDE.md:**
- Du fragst: "Schreib mir eine Mail an Max."
- Claude weiß nicht: wer du bist, wer Max ist, welcher Tonfall, welches Anliegen.
- Antwort ist generisch.

**Mit gepflegter CLAUDE.md:**
- Du fragst: "Schreib mir eine Mail an Max."
- Claude liest CLAUDE.md, weiß: du bist Gründer XYZ, dein Stil ist knapp und freundlich, im Ordner gibt es Projekt-Kontext zu Max.
- Antwort ist spezifisch, klingt nach dir.

Das ist kein bisschen besser - das ist ein anderes Werkzeug.

## Was gehört rein

- **Wer du bist** - Rolle, Kontext, wichtige Details
- **Was der Ordner ist** - Projekt, Produkt, persönliches Wiki
- **Regeln** - Konventionen, Sprache, was vermieden werden soll
- **Pointer** - welche anderen Dateien wichtig sind

Konkrete Anleitung mit Beispielen: [[../second-brain/claude-md-anleitung|CLAUDE.md richtig schreiben]].

## Wo CLAUDE.md liegt

Die App liest CLAUDE.md aus dem aktuell verbundenen Workspace-Ordner. Wenn du mehrere Workspaces hast (Wiki, Projekt A, Projekt B), kann jeder seine eigene CLAUDE.md haben.

Zusätzlich gibt es einen globalen Kontext den Claude überall liest. Den kannst du in den App-Einstellungen unter "Persönliche Anweisungen" oder ähnlichem Namen pflegen. Dort kommt rein was für alle Workspaces gilt (Sprache, Stil, generelle Regeln).

## Warum ein Wiki

Eine CLAUDE.md alleine reicht für einfache Setups. Sobald du mehrere Themen, Projekte und Entscheidungen managst, brauchst du Struktur drum herum: ein Wiki.

Ein Wiki ist ein Ordner mit Markdown-Dateien, strukturiert wie du es brauchst:

```
mein-wiki/
├── CLAUDE.md            ← Einstieg fuer Claude
├── projects/            ← deine Projekte
├── reference/           ← Nachschlagewerk
├── daily/               ← Tagesnotizen
└── inbox.md             ← Quick Capture
```

Claude liest bei Bedarf die richtige Datei. Du musst nicht alles in den Prompt schreiben.

Komplette Anleitung zum Wiki-Aufbau im Bereich [[../second-brain/warum|Second Brain]].

## Der Effekt mit allem zusammen

| Setup | Antwort auf "Was steht heute an?" |
|---|---|
| Nur Web-Chat | "Das hängt von deinen Zielen ab. Magst du mir mehr erzählen?" |
| Claude Code mit verbundenem Ordner | "Im Ordner sehe ich folgende Dateien... worum geht es konkret?" |
| Mit CLAUDE.md | "Du bist Gründer XYZ. Was ist gerade dein Hauptthema?" |
| Mit Wiki + CLAUDE.md | "Drei Prioritäten: Bug fixen in Projekt A, Konzept fertigstellen für Kunde B, Mail an C beantworten. Soll ich loslegen?" |

Der letzte Setup-Level ist der Punkt an dem Claude Code wirklich Zeit zurückgibt.

## Wann du anfangen solltest

**Sofort.** Auch mit einer minimalen CLAUDE.md von 10 Zeilen. Auch wenn das Wiki erstmal aus zwei Dateien besteht. Du wächst rein, perfekt-am-Anfang ist eine Falle.

Konkreter Pfad:
1. Heute: CLAUDE.md anlegen mit Wer-du-bist und Sprache/Stil
2. Diese Woche: ein erstes Projekt als context.md anlegen
3. Nächste Woche: zweites Projekt
4. Nach 4 Wochen: du hast ein laufendes System und willst nicht mehr ohne arbeiten

:::tip[Wichtigster Punkt im Guide]
Wenn du nur eine Sache aus diesem ganzen Guide mitnimmst: leg eine CLAUDE.md an. Heute. Ohne lange darüber nachzudenken. Das ist der größte einzelne Hebel den es bei Claude Code gibt.
:::
