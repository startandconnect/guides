---
title: Wiki und CLAUDE.md
order: 5
excerpt: Die wichtigste Angewohnheit - Kontext permanent verfuegbar machen
---

# Wiki und CLAUDE.md

Wenn du Claude Code ernsthaft nutzen willst, brauchst du einen Ort an dem dein Kontext lebt. Dieser Ort ist ein Wiki plus eine CLAUDE.md Datei.

## Was ist CLAUDE.md

Eine Markdown-Datei die Claude Code automatisch liest, wenn du es in einem Verzeichnis startest. Dort steht alles was Claude wissen muss: wer du bist, woran du arbeitest, welche Regeln gelten.

TODO: Minimalbeispiel und Maximalbeispiel, beides kommentiert.

## Was gehoert rein

- **Wer du bist** - Rolle, Kontext, wichtige Details
- **Was der Ordner ist** - Projekt, Produkt, persoenliches Wiki
- **Regeln** - Konventionen, Sprache, was vermieden werden soll
- **Pointer** - welche anderen Dateien wichtig sind

TODO: Strukturvorschlag, Reihenfolge der Abschnitte.

## Globale CLAUDE.md

Neben der projekt-spezifischen gibt es eine globale Version unter `~/.claude/CLAUDE.md`. Dort kommt rein, was fuer alle Projekte gilt.

TODO: Was global hingehoert vs was projekt-lokal bleibt.

## Wiki

Die CLAUDE.md verweist ins Wiki. Ein Wiki ist ein Ordner mit Markdown-Dateien, strukturiert wie du es brauchst. Claude Code liest bei Bedarf die richtige Datei.

TODO: Beispiel-Wiki-Struktur, wann ein Wiki sinnvoll ist, wann eine einzelne Datei reicht.

## Der Effekt

Ohne CLAUDE.md: Claude raet bei jeder Frage.
Mit CLAUDE.md: Claude weiss sofort Kontext und kann fokussiert antworten.
Mit Wiki: Claude kann dir zu jedem Thema Zugriff geben, ohne dass du alles in den Prompt schreibst.

TODO: Vorher-Nachher-Vergleich an konkretem Beispiel.
