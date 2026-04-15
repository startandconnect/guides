---
title: Die Struktur
order: 2
excerpt: Ordner, Dateinamen und Konventionen die sich bewährt haben
---

# Die Struktur

Ein gutes Second Brain hat wenige Ordner und klare Regeln. Lieber flach und streng als tief und chaotisch.

## Die Basis-Struktur

```
mein-wiki/
├── CLAUDE.md          ← Einstieg für Claude Code
├── README.md          ← Einstieg für Menschen (inkl. dich selbst in 6 Monaten)
├── inbox.md           ← Quick Capture: alles was schnell rein muss
├── daily/             ← Tagesnotizen (YYYY-MM-DD.md)
├── projects/          ← Deine Projekte, einer pro Ordner
├── reference/         ← Nachschlagewerk (APIs, Prozesse, Listen)
└── meetings/          ← Meeting-Notizen
```

Das ist alles. Wenn du anfängst, brauchst du weniger als die Hälfte.

TODO: Baumansicht mit Beispiel-Inhalten.

## Die Regeln

1. **CLAUDE.md ist Pflicht.** Die erste Datei. Hier steht was Claude wissen muss.
2. **context.md pro Projekt.** Jeder Projekt-Ordner hat eine context.md mit Status, Zielen, offenen Punkten.
3. **Dateinamen klein und mit Bindestrichen.** `not-alone.md`, nicht `Not Alone.md`.
4. **Dateinamen auf Englisch, Inhalt auf Deutsch.** Verhindert Umlauten-Chaos in Pfaden.
5. **Echter Inhalt, keine Platzhalter.** Lieber 3 Zeilen als 3 Seiten "wird noch ergänzt".

TODO: Jede Regel mit Begründung und Beispiel.

## context.md als wichtigste Datei pro Projekt

```markdown
# Projekt XYZ

**Status:** Aktiv | Blockiert | Pausiert | Abgeschlossen
**Typ:** Eigenes Produkt | Kundenprojekt | Lernprojekt

## Was ist das Projekt

Ein Satz. Zwei wenn nötig.

## Ziele

- Was soll bis wann erreicht sein

## Offene Themen

- [ ] Aufgabe 1
- [ ] Aufgabe 2

## Entscheidungen

- YYYY-MM-DD: Warum X statt Y

## Chronologie

- YYYY-MM-DD: was passiert ist
```

TODO: context.md Variationen für verschiedene Projekttypen.

## Was du NICHT machen solltest

- **Tiefe Verschachtelung.** Mehr als zwei Ebenen tief ist meist schon zu viel.
- **Generische Ordner wie `docs/`, `notes/`, `misc/`.** Entweder klarer Name oder weg.
- **Daten aus Produktivsystemen kopieren.** Kundendaten, API Keys, Passwörter - niemals.
- **Alles auf einmal aufsetzen.** Fang minimal an, lass es wachsen.

:::tip[Pragmatismus]
Wenn du nach einer Woche merkst "Ordner X nutze ich nie" - weg damit. Struktur ist ein Werkzeug, kein Denkmal.
:::
