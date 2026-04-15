---
title: Mental Model - alles oder nichts
order: 4
excerpt: Warum Claude Code in den Händen von Profis alles kann und bei Anfängern nichts
---

# Mental Model: alles oder nichts

Claude Code ist das seltsamste Werkzeug, mit dem ich je gearbeitet habe. In den Händen von jemandem der weiß was er will, baut es in Stunden was früher Wochen gedauert hat. In den Händen von jemandem der nicht weiß was er will, produziert es stundenlang Müll.

## Warum das so ist

Claude macht keine Entscheidungen für dich. Es fragt selten nach, wenn etwas unklar ist - es rät. Wer den Kontext nicht vorgibt, bekommt irgendein Ergebnis, nicht das richtige.

### Beispiel: "Schreib mir eine Mail"

**Ohne Kontext:** "Schreib mir eine Mail an Max."
- Ergebnis: generische Mail in irgendeinem Stil, irgendeiner Länge, irgendeinem Anliegen
- Du musst neu anfangen oder massiv überarbeiten

**Mit Kontext:** "Schau in projects/kunde-max/context.md was wir besprochen haben. Schreib eine Mail an Max mit Status-Update zum Projekt. Tonalität wie in meiner CLAUDE.md beschrieben."
- Ergebnis: spezifische Mail die zum Kunden, zum Projekt und zu deinem Stil passt

Der Unterschied: 30 Sekunden mehr Tipparbeit für den Prompt sparen 5 Minuten Nacharbeit.

## Was erfahrene Nutzer anders machen

### 1. Sie haben ein Wiki oder mindestens eine CLAUDE.md

Ohne strukturierten Kontext ist jeder Chat ein Neustart. Mit Wiki + CLAUDE.md hat Claude permanenten Kontext.

**Beispiel:** Ein erfahrener Nutzer fragt "Was steht heute an?" und bekommt eine konkrete Antwort. Ein Anfänger fragt "Was steht heute an?" und bekommt "Das hängt davon ab was deine Ziele sind." Gleicher Prompt, völlig unterschiedliches Ergebnis - weil der eine den Kontext gepflegt hat.

### 2. Sie brechen Aufgaben in kleine Stufen

Schlecht: "Bau mir eine komplette Landingpage."
Gut: "Lass uns Schritt für Schritt eine Landingpage bauen. Schritt 1: Skizziere mir die Sektionen die wir brauchen, basierend auf der Zielgruppe in projects/X/context.md."

Nach Bestätigung: Schritt 2. Nach Bestätigung: Schritt 3. So bleibt jede Stufe prüfbar.

### 3. Sie prüfen Zwischenergebnisse, nicht nur das Endergebnis

Wenn Claude 10 Dateien anpasst und du erst am Ende guckst, hast du keine Chance zu verstehen wo es schiefging. Nach jeder Anpassung kurz prüfen.

### 4. Sie kennen die Grenzen ihres eigenen Verständnisses

Wenn du selbst nicht klar definieren kannst was du willst - kann Claude es auch nicht. Erst denken, dann fragen.

## Die drei Levels

### Level 1: Prompter

Du nutzt Claude wie eine bessere Suchmaschine. Einzelne Fragen, einzelne Antworten. Was du bekommst kopierst du raus, ergänzt selbst.

**Typisch:** Web-Chat oder die App ohne verbundenen Ordner. Funktioniert für gelegentliche Aufgaben.

### Level 2: Operator

Du gibst Claude einen Ordner, lässt es Dateien lesen und schreiben. Aufgaben werden komplett in der App erledigt.

**Typisch:** Wiki pflegen, Dokumente umstrukturieren, Konzepte erarbeiten. Spart massiv Zeit bei wiederkehrenden Aufgaben.

### Level 3: Architekt

Du hast ein Wiki mit klarer Struktur. CLAUDE.md ist gepflegt. Du nutzt Skills für Routine. Du denkst in Workflows statt in Prompts.

**Typisch:** Dein Wiki ist Teil deines täglichen Arbeitens. Claude kennt deinen Kontext. Aufgaben die früher Stunden brauchten sind in Minuten erledigt.

### Übergänge

- **Level 1 → 2:** App installieren, ersten Ordner verbinden, ersten echten Workflow durchziehen.
- **Level 2 → 3:** Wiki strukturieren, CLAUDE.md ernsthaft pflegen, Skills für die drei häufigsten Aufgaben anlegen.

Die meisten Menschen bleiben auf Level 1 hängen - nicht weil das Tool schlecht ist, sondern weil sie nie den Sprung zu Level 2 probieren. Der Sprung dauert eine Stunde Setup und eine Woche Eingewöhnung. Danach ist es ein anderes Werkzeug.

## Anti-Muster

### "Claude hat halluziniert"

Manchmal stimmt das. Oft heißt das aber: "Ich habe Claude nicht genug Kontext gegeben und nicht genug geprüft." Bevor du Claude die Schuld gibst: war dein Prompt klar, war der Kontext da, hast du Zwischenergebnisse geprüft?

### "Claude ist nicht so gut wie X"

Vergleiche bringen wenig wenn dein Setup mittelmäßig ist. Ein Anfänger mit Cursor wird von einem Profi mit Claude Code überholt - und umgekehrt. Das Tool macht 30 Prozent aus, dein Setup 70 Prozent.

### "Ich hab keine Zeit das richtig aufzusetzen"

Die Stunde Setup spart in den nächsten 30 Tagen mindestens 10 Stunden. Wer "keine Zeit" hat ist meist in der Endlosschleife "ich mache es schnell selbst, weil keine Zeit zum Aufsetzen" - und macht es danach 100 mal.

:::tip[Ehrliche Einschätzung]
Die meisten bleiben auf Level 1 hängen, nicht weil das Tool schlecht ist, sondern weil sie nie den zweiten Schritt probieren. Der Guide hilft dir, Level 2 und 3 zu erreichen.
:::
