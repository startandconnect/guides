---
title: Skills, Hooks und Subagents
order: 7
excerpt: Die Power-Features - wann du sie brauchst, wann nicht
---

# Skills, Hooks und Subagents

Claude Code hat drei Erweiterungsmechanismen. Sie sind kein Muss am Anfang, aber sobald du öfter mit dem Tool arbeitest, lohnt sich der Blick.

## Skills

Wiederverwendbare Anweisungen für ein bestimmtes Vorgehen. Beispiel: "Commit-Skill" - wenn du "/commit" aufrufst, liest Claude die Änderungen und erstellt einen sauberen Commit.

TODO: Ein echtes Skill-Beispiel komplett durchspielen.

## Hooks

Automatisierungen, die vor oder nach bestimmten Aktionen laufen. Beispiel: nach jedem Speichern automatisch formatieren, vor jedem Commit Tests laufen lassen.

TODO: Hook-Syntax zeigen, zwei Beispiele.

## Subagents

Spezialisierte Agents, die Claude selbst aufruft für bestimmte Aufgaben. Beispiel: Code-Review-Agent, der einen frischen Blick auf Änderungen wirft.

TODO: Wann Subagent besser als normaler Prompt, Beispiel.

## Wann man diese Features braucht

- **Skills:** sobald du den gleichen Prompt zum dritten Mal tippst
- **Hooks:** sobald du dieselbe Nachbereitung zum dritten Mal manuell machst
- **Subagents:** sobald du einen zweiten, unabhängigen Blick auf ein Ergebnis willst

TODO: Beispiele für "Ah, dafür braucht man Skills/Hooks/Subagents".

:::tip[Ehrlich]
Die meisten brauchen erstmal nichts davon. Fang mit normalen Prompts an. Diese Features kommen, wenn du sie brauchst.
:::
