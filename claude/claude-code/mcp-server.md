---
title: MCP Server anbinden
order: 8
excerpt: Claude Code mit anderen Tools verbinden - Notion, GitHub, Slack und mehr
---

# MCP Server anbinden

MCP (Model Context Protocol) ist die Schnittstelle mit der Claude Code andere Tools anspricht. Statt Daten zu kopieren, redet Claude direkt mit dem Tool.

## Was MCP ermöglicht

- Notion durchsuchen und Seiten erstellen
- GitHub Issues lesen und anlegen
- Slack Nachrichten lesen und schreiben
- Eigene APIs anbinden

TODO: Aktuelle Liste der wichtigsten MCP Server.

## Wie einen Server hinzufügen

TODO: Konkreter Befehl, Beispiel mit Notion MCP.

## Eigenen MCP Server bauen

Wenn es für dein Tool keinen fertigen Server gibt, kannst du einen eigenen schreiben. Nicht trivial, aber machbar.

TODO: Hinweis auf offizielle Docs, Minimal-Beispiel.

## Wann MCP lohnt

- Wenn du oft Daten zwischen zwei Tools händisch kopierst
- Wenn du Claude Code oft Fragen stellst, die Zugriff auf ein externes System bräuchten
- Wenn du regelmäßig Aktionen in einem anderen Tool triggern willst

TODO: Beispiele für typische MCP-Workflows.

:::tip[Sicherheit]
Ein MCP Server kann Daten lesen und Aktionen auslösen. Verbinde nur Tools, denen du vertraust, und verstehe was der Server darf.
:::
