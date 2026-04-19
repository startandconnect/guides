---
title: Skills, Hooks und Subagents
order: 7
excerpt: Die Power-Features - wann du sie brauchst, wann nicht
---

# Skills, Hooks und Subagents

Claude Code hat Erweiterungsmechanismen die Routine-Aufgaben automatisieren. Sie sind kein Muss am Anfang, aber sobald du öfter mit dem Tool arbeitest, lohnt sich der Blick.

## Skills

Wiederverwendbare Anweisungen für ein bestimmtes Vorgehen. Einmal definiert, einfach abrufbar.

**Beispiel: Tagesstart-Skill**

Du machst jeden Morgen die gleichen Schritte: Wiki scannen, Prioritäten klären, Tagesfile anlegen. Statt das jeden Tag zu erklären, baust du einen Skill der das automatisch macht.

In der App: **Skill anlegen** (über Einstellungen oder das Skill-Menü):

- Name: `Tagesstart`
- Trigger: wenn du `/tagesstart` schreibst oder den Skill aus dem Menü wählst
- Anweisung: Lies CLAUDE.md, scanne aktive Projekte, schlage drei Prioritäten vor, lege das Tagesfile an

Ab jetzt: einmal `/tagesstart` in der App, und Claude führt alle Schritte aus.

**Wann ein Skill sinnvoll ist**

- Du tippst denselben Prompt zum dritten Mal
- Die Aufgabe hat klare Schritte die immer gleich sind
- Du willst einer Routine einen Namen geben

**Wann nicht**

- Einmalige Aufgaben
- Sehr unterschiedliche Varianten des gleichen Themas
- Wenn der Skill am Ende doch immer manuell angepasst werden muss

## Hooks

Automatisierungen die vor oder nach bestimmten Aktionen laufen. Hooks brauchst du seltener als Skills, aber für bestimmte Disziplin-Themen sind sie unschlagbar.

**Beispiele**

- Vor jedem Speichern automatisch formatieren
- Nach jeder Session eine Erinnerung "context.md aktualisiert?"
- Vor jedem Commit prüfen ob die Datei keine API Keys enthält

In der App findest du Hooks normalerweise unter "Erweiterte Einstellungen" oder ähnlich. Sie sind eher etwas für Profis.

**Wann Hooks lohnen**

- Du machst denselben Nachbereitungsschritt zum dritten Mal manuell
- Du willst eine Disziplin durchsetzen die du sonst vergisst

## Subagents

Spezialisierte Helfer die Claude für bestimmte Aufgaben aufruft. Statt einen großen Prompt zu schreiben, sagst du Claude "ruf für diesen Teil den Code-Review-Subagent auf".

**Beispiel: Code-Review-Subagent**

Du arbeitest an einer Datei, hast viel geändert, willst einen frischen Blick darauf.

In der App: "Lass den Code-Review-Subagent meine letzten Änderungen prüfen."

Der Subagent öffnet einen separaten Kontext, schaut sich die Änderungen an, gibt Feedback. Vorteil: er hat keine Voreingenommenheit aus dem Hauptchat.

**Wann Subagents**

- Du willst einen unabhängigen, frischen Blick
- Eine Aufgabe ist so groß dass sie einen eigenen Kontext braucht
- Du willst parallel arbeiten lassen (Subagent in Hintergrund, du machst was anderes)

## Wann man diese Features braucht

- **Skills:** sobald du den gleichen Prompt zum dritten Mal tippst
- **Hooks:** sobald du dieselbe Nachbereitung zum dritten Mal manuell machst
- **Subagents:** sobald du einen zweiten, unabhängigen Blick auf ein Ergebnis willst

Bei keinem dieser Features brauchst du Code-Wissen. Du beschreibst was passieren soll, Claude bzw. die App machen den Rest.

## Wo du diese Features findest

In der Claude App: meistens unter "Einstellungen" oder einem dedizierten Menü-Punkt. Die genaue UI ändert sich öfter - wenn du etwas nicht findest, einfach Claude in der App fragen: "Wie lege ich einen Skill an?"

## Was wenn die Features in deiner Variante fehlen

Skills, Hooks und Subagents sind teilweise an Subscription-Stufen geknüpft. Wenn dir Features fehlen: prüfe ob du auf der richtigen Plan-Stufe bist (Pro reicht meistens).

:::tip[Ehrlich]
Die meisten brauchen erstmal nichts davon. Fang mit normalen Prompts und einer guten CLAUDE.md an. Diese Features kommen, wenn du sie brauchst - nicht weil sie cool klingen.
:::
