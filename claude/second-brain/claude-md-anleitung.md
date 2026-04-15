---
title: CLAUDE.md richtig schreiben
order: 5
excerpt: Die wichtigste Datei im Second Brain - Aufbau, Stil, typische Fehler
---

# CLAUDE.md richtig schreiben

Die CLAUDE.md ist das erste was Claude Code liest wenn du den Ordner öffnest. Alles was dort nicht steht, muss in jedem Prompt erklärt werden. Wer CLAUDE.md gut schreibt, spart sich bei jeder Frage mehrere Sätze.

## Die drei Ebenen

Claude Code liest CLAUDE.md auf drei Ebenen (von unten nach oben):

1. **Projekt-lokal:** `./CLAUDE.md` im aktuellen Ordner
2. **User-übergreifend:** `~/.claude/CLAUDE.md` für alle Projekte auf diesem Rechner
3. **Enterprise:** (falls dein Team eine gemeinsame Policy hat)

Alle drei werden gelesen und zusammengefügt. Global steht was allgemein gilt, lokal was projektspezifisch ist.

TODO: Beispiele für global vs lokal.

## Was gehört in die lokale CLAUDE.md

- **Wer du bist** (Rolle, Firma, Kontext)
- **Was dieses Wiki ist** (Second Brain? Projekt-Wiki? Firmen-Wiki?)
- **Sprache und Stil** (Deutsch/Englisch, du/Sie, Umlaute, keine Dashes)
- **Wichtige Regeln** (was nie tun, was immer tun)
- **Pointer** (welche anderen Dateien sollte Claude bei Bedarf lesen)

## Aufbau einer guten CLAUDE.md

```markdown
# Wer ich bin

[Name], [Rolle]. Ich arbeite an [Hauptprojekt].

# Was dieses Wiki ist

Mein persönliches Second Brain. Hier leben Projekte, Referenzen, Notizen.

# Sprache und Stil

- Deutsch, außer technische Begriffe
- Echte Umlaute (ä, ö, ü, ß) in Texten
- Dateinamen auf Englisch mit Bindestrichen
- Keine Dashes (– oder —), nur normale Bindestriche

# Regeln

- Erledigte Aufgaben sofort als [x] markieren
- Nach jeder Arbeitssession: context.md updaten
- Niemals API Keys oder Kundendaten in Dateien

# Struktur

- projects/ - pro Projekt ein Ordner mit context.md
- daily/ - Tagesnotizen (YYYY-MM-DD.md)
- reference/ - Nachschlagewerk
- inbox.md - für alles was schnell rein muss
```

TODO: Vollständiges Beispiel in Langversion.

## Was NICHT reingehört

- **Passwörter und Keys** (auch nicht "zum Testen")
- **Sehr langer Text** (mehr als 2 Bildschirmseiten ist meist zu viel)
- **Inhalte die sich oft ändern** (landen in separaten Dateien, nicht hier)
- **Marketing-Sprache** ("ich bin passioniert", "wir lieben Innovation")
- **Alles was du nicht wirklich meinst** (Claude hält sich dran, bei Widersprüchen wird es merkwürdig)

## Typische Fehler

### Fehler 1: Zu lang
CLAUDE.md wird bei jeder Frage mitgeladen. Zu lang = Token-Verschwendung und Rauschen.

### Fehler 2: Zu vage
"Arbeite sorgfältig" ist wertlos. "Sprache: Deutsch, du-Form, keine Dashes" ist konkret.

### Fehler 3: Widersprüche
Wenn CLAUDE.md "sei kurz" sagt und du gleichzeitig lange Essays erwartest, wird Claude verwirrt.

### Fehler 4: Copy-Paste von fremden Templates
Eine CLAUDE.md die nicht zu dir passt ist schlechter als gar keine. Bau sie selbst.

TODO: Jeden Fehler mit Gegenbeispiel.

## Pflege

Die CLAUDE.md ist kein Denkmal. Sie lebt:

- **Jedes Mal wenn du Claude dreimal dasselbe erklärt hast:** rein in die CLAUDE.md.
- **Jedes Mal wenn Claude was macht was du nicht wolltest:** Regel formulieren, rein in die CLAUDE.md.
- **Jedes Quartal:** überfliegen, veraltetes raus.

:::tip[Beobachtung]
Eine gute CLAUDE.md wirkt wie ein Onboarding-Dokument für einen neuen Mitarbeiter. Wenn du es einem Menschen geben würdest und er könnte danach arbeiten - dann ist es gut.
:::
