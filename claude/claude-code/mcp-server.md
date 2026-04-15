---
title: MCP Server und Connectors
order: 8
excerpt: Claude Code mit anderen Tools verbinden - Notion, GitHub, Slack und mehr
---

# MCP Server und Connectors

MCP (Model Context Protocol) ist die Schnittstelle mit der Claude Code andere Tools anspricht. Statt Daten zu kopieren, redet Claude direkt mit dem Tool.

In der Claude App heißen diese Verbindungen meist "Connectors" oder "Integrationen".

## Was Connectors ermöglichen

- Notion durchsuchen und Seiten erstellen
- GitHub Issues lesen und anlegen
- Slack Nachrichten lesen und schreiben
- Google Drive Dokumente öffnen
- Stripe Daten abfragen
- Eigene Tools anbinden

Statt zwischen Apps zu switchen und manuell zu kopieren, lässt du Claude direkt mit dem System arbeiten.

## Wie einen Connector hinzufügen

In der Claude App:

1. **Einstellungen** → **Connectors** (oder "Integrationen")
2. Connector aus der Liste wählen (z.B. Notion)
3. Auf **Verbinden** klicken
4. Im aufpoppenden Browser-Fenster bei dem Service einloggen und Berechtigung geben
5. Zurück in die App - der Connector ist aktiv

Ab jetzt kann Claude auf Notion zugreifen. Beispiel-Frage:

> Suche in meinem Notion nach Notizen zum Thema "Onboarding" und fasse zusammen.

Claude greift via Connector auf Notion zu, findet die Seiten, fasst zusammen.

## Welche Connectors es gibt

Anthropic pflegt eine Liste offizieller Connectors. Die wichtigsten typischerweise:

- **Notion** - Seiten lesen und erstellen
- **GitHub** - Issues, PRs, Code lesen
- **Google Drive** - Dokumente und Sheets
- **Slack** - Channels, Messages
- **Linear** - Issues und Projekte
- **Sentry** - Error Logs

Die Liste wächst regelmäßig. Was es aktuell gibt, siehst du in der App unter Connectors.

## Connector-Berechtigungen

Wichtig: jeder Connector bekommt nur das was du ihm gibst. Beim Hinzufügen wirst du gefragt welche Berechtigungen Claude bekommen soll.

**Empfehlung:**
- Erstmal nur Lese-Berechtigung geben
- Schreib-Berechtigung erst wenn du sicher bist dass es funktioniert
- Zugriff auf einzelne Bereiche statt "alles" wenn möglich

Du kannst Berechtigungen jederzeit wieder entziehen über die App-Einstellungen oder beim externen Service direkt.

## Eigenen MCP Server bauen

Wenn es für dein Tool keinen fertigen Connector gibt, kannst du einen eigenen MCP Server schreiben. Das ist allerdings ein technisches Projekt - braucht Programmier-Wissen.

Wenn du dich rantraust:

- Anthropic MCP Spec: modelcontextprotocol.io
- TypeScript- oder Python-SDK
- Beispiele im offiziellen Anthropic GitHub-Repo

Für 95 Prozent der Anwender reicht die Liste vorhandener Connectors.

## Wann Connectors lohnen

- Wenn du oft Daten zwischen zwei Tools händisch kopierst
- Wenn du Claude oft Fragen stellst, die Zugriff auf ein externes System brauchen
- Wenn du regelmäßig Aktionen in einem anderen Tool triggern willst

### Beispiel-Workflows

**Newsletter-Brainstorming mit Notion**
> Schau in meinem Notion-Workspace welche Themen ich in den letzten 4 Wochen recherchiert habe. Schlage drei davon als Newsletter-Themen vor.

**Issue-Management mit GitHub**
> Liste alle offenen Issues im Repo X die als "bug" gelabelt sind. Welche sind kritisch?

**Slack-Zusammenfassung**
> Fasse die wichtigsten Diskussionen aus #team-product der letzten Woche zusammen.

## Was wenn Connector nicht funktioniert

- **Login abgelaufen:** in den Connector-Einstellungen neu verbinden
- **Falsche Berechtigungen:** prüfen ob Claude wirklich Zugriff auf den Bereich hat
- **Service-Ausfall:** beim externen Service nachsehen ob der gerade läuft
- **Connector veraltet:** App auf neueste Version updaten

:::tip[Sicherheit]
Ein Connector kann Daten lesen und Aktionen auslösen. Verbinde nur Tools denen du vertraust, gib nur die Berechtigungen die du wirklich brauchst, und prüfe die Liste der Connectors regelmäßig.
:::
