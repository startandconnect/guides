---
title: CLAUDE.md richtig schreiben
order: 5
excerpt: Die wichtigste Datei im Second Brain - Aufbau, Stil, typische Fehler
---

# CLAUDE.md richtig schreiben

Die CLAUDE.md ist das erste was Claude Code liest wenn du den Ordner öffnest. Alles was dort nicht steht, muss in jedem Prompt erklärt werden. Wer CLAUDE.md gut schreibt, spart sich bei jeder Frage mehrere Sätze.

## Die drei Ebenen

Claude Code liest Kontext auf zwei Ebenen:

1. **Workspace-lokal:** `CLAUDE.md` im verbundenen Ordner
2. **App-global:** "Persönliche Anweisungen" in den App-Einstellungen, gelten für alle Workspaces

Beides wird kombiniert. Global steht was allgemein gilt, lokal was workspace-spezifisch ist.

### Was global gehört (App-Einstellungen)

- Wer du bist (Name, Rolle, Firma)
- Welche Sprache du nutzt (Deutsch, du-Form)
- Stil-Konventionen (Umlaute, keine Dashes, kurze Antworten)
- Generelle Regeln die für alles gelten

Diese Inhalte hinterlegst du einmal in den App-Einstellungen unter "Persönliche Anweisungen" (Name kann je nach App-Version leicht abweichen). Claude liest sie bei jedem Chat in jedem Workspace mit.

### Was lokal gehört (Wiki-Ordner `CLAUDE.md`)

- Was dieses spezifische Wiki ist
- Struktur des Wikis (welche Ordner gibt es, was steht wo)
- Wiki-spezifische Regeln (Session-Logs anlegen, context.md aktualisieren)
- Pointer auf wichtige Dateien

So vermeidest du Wiederholung. Globale Sachen einmal in den App-Einstellungen, lokale Sachen pro Wiki in der CLAUDE.md.

## Was gehört in die lokale CLAUDE.md

- **Wer du bist** (Rolle, Firma, Kontext) - falls nicht in global
- **Was dieses Wiki ist** (Second Brain? Projekt-Wiki? Firmen-Wiki?)
- **Sprache und Stil** (Deutsch/Englisch, du/Sie, Umlauten-Regel, keine Dashes)
- **Wichtige Regeln** (was nie tun, was immer tun)
- **Pointer** (welche anderen Dateien sollte Claude bei Bedarf lesen)

## Aufbau einer guten CLAUDE.md - kurzes Beispiel

```markdown
# Wer ich bin

Ben Scheurer, Gründer von Start & Connect (SaaS-Agentur).
Hauptthemen: Nexus (eigenes SaaS), Kundenprojekte, YouTube.

# Was dieses Wiki ist

Mein persönliches Second Brain. Alle Projekte, Referenzen,
Entscheidungen leben hier.

# Sprache und Stil

- Deutsch, technische Begriffe und Code auf Englisch
- Echte Umlaute (ä, ö, ü, ß), nie ae/oe/ue
- Du-Form, kein "Sie"
- Keine Dashes (en/em dash), nur normale Bindestriche

# Regeln

- Erledigte Aufgaben sofort als [x] markieren
- Nach jeder Arbeitssession: betroffene context.md updaten
- Niemals API Keys oder Kundendaten in Dateien
- Bei wichtigen Entscheidungen: in DECISIONS.md eintragen

# Struktur

- projects/ - aktive Projekte, eines pro Ordner mit context.md
- sessions/ - Tagesnotizen (YYYY-MM-DD.md)
- reference/ - Nachschlagewerk (APIs, Prozesse)
- meetings/ - Meeting-Notes (YYYY-MM-DD-thema.md)
- INBOX.md - Quick Capture, später einsortieren
```

Das sind 30 Zeilen. Mehr brauchst du am Anfang nicht.

## Aufbau einer guten CLAUDE.md - ausführliches Beispiel

Wenn dein Wiki komplexer wird (mehrere Produkte, Kunden, Workflows):

```markdown
# Wer ich bin

Ben Scheurer, Gründer von Start & Connect.

Wir bauen SaaS-Produkte (Nexus, Spotlight) und betreuen Kunden mit
individuellen Lösungen.

# Kontext-Hierarchie

Lies Dateien in dieser Reihenfolge, je nach Aufgabe:

1. CLAUDE.md (diese Datei) + planning/TODAY.md (aktuelle Aufgaben)
2. Pro Produkt: products/<name>/context.md
3. Pro Kundenprojekt: projects/<name>/context.md
4. Bei Bedarf: reference/, runbooks/

Nicht alles auf einmal lesen. Nur was relevant ist.

# Sprache

Deutsch als Standardsprache. Technische Begriffe und Code auf Englisch.
Echte Umlaute (ä, ö, ü, ß) - niemals ae, oe, ue, ss als Ersatz.
Keine Dashes (- oder -), nur normale Bindestriche.

# Regeln

1. context.md ist die wichtigste Datei pro Projekt
2. Aufgaben immer als Checkboxen ([- ] und [x])
3. Erledigte Aufgaben sofort abhaken, nicht auf Aufforderung warten
4. Session-Log: eine Datei pro Tag in sessions/, nie überschreiben
5. Nach jeder Session: context.md, DECISIONS.md, CHANGELOG.md updaten

# Tools

Alle Tools per direkter API ansprechen, nicht per MCP suchen.
API-Keys liegen in ~/.env.sac.

# Effizienz

- Grep vor Read - bei großen Dateien gezielt suchen
- Tool-Calls parallelisieren wenn unabhängig
- Keine Datei zweimal lesen
- Hintergrund-Agenten nutzen für unabhängige Arbeit
```

Das ist ein produktives Beispiel. Du kannst erkennen wie spezifisch die Regeln sind - keine Floskeln, jede Zeile bringt Wert.

## Was NICHT reingehört

- **Passwörter und Keys** (auch nicht "zum Testen")
- **Sehr langer Text** (mehr als 2 Bildschirmseiten ist meist zu viel)
- **Inhalte die sich oft ändern** (landen in separaten Dateien, nicht hier)
- **Marketing-Sprache** ("ich bin passioniert", "wir lieben Innovation")
- **Alles was du nicht wirklich meinst** (Claude hält sich dran, bei Widersprüchen wird es merkwürdig)

## Typische Fehler

### Fehler 1: Zu lang

CLAUDE.md wird bei jeder Frage mitgeladen. Zu lang heißt Token-Verschwendung und Rauschen.

**Schlecht:** 200 Zeilen mit jeder denkbaren Regel.
**Gut:** 30 bis 60 Zeilen mit den wichtigsten Regeln. Spezifischeres in dedizierte Dateien.

### Fehler 2: Zu vage

"Arbeite sorgfältig" ist wertlos. Was heißt sorgfältig?

**Schlecht:** "Schreib gute Texte."
**Gut:** "Texte: Deutsch, du-Form, kurze Sätze, keine Marketing-Floskeln. Beispiele für gute Tonalität: README.md im Repo."

### Fehler 3: Widersprüche

Wenn CLAUDE.md "sei kurz" sagt und du gleichzeitig lange Essays erwartest, wird Claude verwirrt. Eine Anweisung gewinnt, die andere verliert - du weißt nicht welche.

**Schlecht:** "Sei kurz und prägnant" + "Erkläre alles ausführlich"
**Gut:** "Antworten kurz und konkret. Wenn ich explizit Tiefe will, sage ich das."

### Fehler 4: Copy-Paste von fremden Templates

Eine CLAUDE.md die nicht zu dir passt ist schlechter als gar keine. Du bekommst Antworten die zu jemand anderem passen, nicht zu dir.

**Schlecht:** Bens CLAUDE.md komplett kopieren weil sie gut aussieht.
**Gut:** Bens CLAUDE.md als Inspiration nehmen, eigene Version schreiben mit deinen Regeln.

## Pflege

Die CLAUDE.md ist kein Denkmal. Sie lebt:

- **Jedes Mal wenn du Claude dreimal dasselbe erklärt hast:** rein in die CLAUDE.md.
- **Jedes Mal wenn Claude was macht was du nicht wolltest:** Regel formulieren, rein in die CLAUDE.md.
- **Jedes Quartal:** überfliegen, veraltetes raus, sich wiederholendes konsolidieren.

## Test: ist meine CLAUDE.md gut

Stelle Claude eine Frage die nur mit Wiki-Kontext gut zu beantworten ist. Beispiel: "Was sind meine drei wichtigsten offenen Aufgaben?"

- Kommt eine spezifische, brauchbare Antwort: gut.
- Kommt eine generische "kommt darauf an" Antwort: CLAUDE.md ist zu vage oder Wiki ist zu leer.
- Fragt Claude erst zurück nach Kontext: CLAUDE.md hat Lücken.

:::tip[Beobachtung]
Eine gute CLAUDE.md wirkt wie ein Onboarding-Dokument für einen neuen Mitarbeiter. Wenn du es einem Menschen geben würdest und er könnte danach arbeiten - dann ist es gut.
:::
