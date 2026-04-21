---
title: MCP (Model Context Protocol)
order: 5
excerpt: Wie KI-Agenten mit externen Tools reden
---

# MCP (Model Context Protocol)

Offenes Protokoll von Anthropic, mit dem KI-Modelle (Claude, GPT, etc.) strukturiert mit externen Tools reden. Eingefuehrt Ende 2024, breiter Industrie-Standard 2025/26.

## Das Problem

Vorher: wenn du wolltest dass Claude auf deine Datenbank schauen kann, musstest du Custom-Code schreiben, der Claude die Daten rueberreicht. Jede Integration = einmalige Bastelei.

MCP standardisiert das: ein MCP-Server beschreibt seine Tools (was er kann), ein MCP-Client (wie Claude) kann sie entdecken und nutzen.

## Das Prinzip

- **MCP-Server** - bietet Tools an. "Ich kann Kundenlisten abrufen, Produkte anlegen, Newsletter versenden."
- **MCP-Client** - (Claude, Cursor, etc.) verbindet sich mit dem Server, sieht die Tool-Liste, entscheidet welches Tool er wann nutzt

## Was das fuer Nexus bedeutet

**Nexus ist MCP-ready.** Das heisst:
- Claude Code kann sich mit deiner Nexus-Instance verbinden
- Claude sieht alle 1000+ API-Endpoints als Tools
- Du sagst "Zeig mir alle Kunden die letzten Monat gekauft aber nicht genutzt haben"
- Claude erzeugt den API-Call, parst die Antwort, gibt dir die Liste

Kein Custom-Tooling noetig. Kein Zapier dazwischen. Claude bedient Nexus wie ein menschlicher Admin.

## Warum das relevant ist

Business-Automation verlagert sich von "Klicks durch UI" zu "Satz an Claude". Tools die MCP-ready sind werden von KI-Agents bedient. Tools die's nicht sind, bleiben manuell.

Vorstellung 2027: Du sagst Claude "Erstelle fuer den Oster-Launch einen Coupon 20 Prozent bis 15. April, Email an die Segmentierung 'Bestandskunden Preis-sensibel', Newsletter-Preview generieren." Claude macht das alles mit Nexus-API-Calls.

## MCP vs klassische APIs

- **Klassische API** - du schreibst den Client
- **MCP-API** - jeder MCP-Client (Claude, GPT, etc.) findet sie automatisch

Nexus-Endpoints sind sowohl REST (direkt aufrufbar) als auch via MCP konsumierbar - beste beider Welten.
