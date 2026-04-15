---
title: Sicherheit - was nie reingeht
order: 10
excerpt: Welche Daten du nie mit Claude teilst und wie du Unfälle vermeidest
---

# Sicherheit: was nie reingeht

Claude Code ist mächtig. Das heißt auch: ein unvorsichtiger Umgang kann teuer werden. Die wichtigsten Regeln.

## Was nie in Workspaces oder Prompts landet

- **API Keys, Passwörter, Tokens** - auch nicht "zum Testen"
- **Produktions-Kundendaten** - echte Namen, Adressen, E-Mails von Kunden
- **Finanzdaten** - Kontonummern, IBAN, Karten
- **Vertrauliche Geschäftsgeheimnisse** - NDA-relevante Inhalte
- **Gesundheitsdaten** - eigene oder fremde

Diese Dinge gehören nicht in deinen Wiki-Ordner und nicht in die Claude App.

## Wie du sensible Daten fernhältst

### 1. Eigener Ordner für Geheimes

Geheimnisse leben außerhalb deines Wiki-Workspaces. Beispiel:

- `~/Documents/mein-brain/` ← dein Wiki, mit Claude verbunden
- `~/Documents/secrets/` ← nicht verbunden, nur du

API Keys, Passwörter etc. landen in dem zweiten Ordner. Claude sieht ihn nie.

### 2. .gitignore nutzen

Dein Wiki ist meist ein Git-Repo. In der `.gitignore` (Datei im Wiki-Hauptordner) listest du was nie committet werden soll:

```
.env
.env.*
*.key
*.pem
secrets.md
private/
```

So landen sensible Dateien nicht versehentlich auf GitHub.

### 3. Vor jedem Commit prüfen

GitHub Desktop zeigt dir vor dem Commit was sich geändert hat. Drüberschauen, sicherstellen dass nichts Heikles dabei ist. Dauert 10 Sekunden, spart im Notfall viel.

## Was tun wenn es doch passiert

### API Key versehentlich rein

1. **Sofort den Key rotieren** beim entsprechenden Service (Stripe, OpenAI, etc.). Der alte Key ist ab sofort wertlos für Angreifer.
2. Wenn schon committet: aus der Datei entfernen, neu committen.
3. Wenn schon gepusht und Repo war public: zusätzlich Repo-History bereinigen (Tools wie `git-filter-repo`). Bei privaten Repos meist unnötig wenn der Key rotiert ist.

### Kundendaten versehentlich rein

1. Datei bereinigen
2. Bei sensiblen Daten (DSGVO-relevant): prüfen ob Meldepflicht besteht
3. Zukünftig Konventionen nutzen: Platzhalter wie "Kunde A" statt echte Namen

## Werkzeugseitige Absicherung

### Berechtigungen in der App

Claude fragt vor wichtigen Aktionen nach Bestätigung. Das ist nicht zum Wegklicken - schau hin was Claude tun will.

**Schlecht:** Auf "Alle Aktionen erlauben" klicken.
**Gut:** Bei jeder Datei-Änderung kurz prüfen, dann bestätigen.

### Workspace-Auswahl bewusst

Du kannst mehrere Workspaces verbinden. Verbinde nur das was Claude wirklich sehen muss. Wenn du an einem privaten Wiki arbeitest, brauchst du nicht zusätzlich den Kunden-Ordner verbunden.

### Connectors mit Vorsicht

Jeder Connector (Notion, GitHub, Slack) bekommt nur die Berechtigungen die du ihm gibst. Faustregel:

- Erst nur lesen
- Schreiben nur wenn nötig
- Keine "alle Repos" wenn ein einzelnes reicht

### Versionierung als Sicherheitsnetz

Wenn dein Wiki ein Git-Repo ist, kannst du jederzeit zu einem älteren Stand zurück. Vor kritischen Aktionen committen, dann hat man immer einen Rollback-Punkt.

## Das richtige Mindset

Claude Code ist wie ein Praktikant mit Root-Zugriff auf einen Teil deines Computers. Gib ihm nicht das, was du einem Praktikanten auch nicht geben würdest.

### Konkrete Beispiele

| Situation | Praktikant würdest du... | Claude Code |
|---|---|---|
| Bankdaten zeigen | Nein | Nein |
| Passwörter teilen | Nein | Nein |
| Kundendatenbank lesen lassen | Nur produktiv & supervised | Nur Test-Daten oder anonymisiert |
| Code-Repo bearbeiten lassen | Ja, mit Code-Review | Ja, du prüfst Änderungen vor Commit |
| Mails schreiben für dich | Ja, du liest vor dem Senden | Ja, du liest vor dem Senden |
| Notizen organisieren | Ja, ohne Aufsicht | Ja, ohne Aufsicht |

## Was Claude nicht macht (und nicht machen kann)

Claude kann nicht "ausbüchsen" und Sachen tun die du nicht autorisierst. Es:

- Liest nur Ordner die du verbunden hast
- Macht nur Aktionen die du bestätigst (bei wichtigen Dingen)
- Hat keinen Internet-Zugriff für eigene Aktionen außer über Connectors die DU eingerichtet hast
- Schickt nichts ohne deine Anweisung

Wenn dir trotzdem Bedenken hast: weniger sensible Daten im Workspace, keine Schreib-Connectors zu kritischen Systemen.

## DSGVO und Datenschutz

Wenn du mit Kundendaten arbeitest:

- Anthropic ist ein US-Unternehmen, Datenschutz-rechtlich relevant
- Für DSGVO-konforme Verarbeitung: AVV (Auftragsverarbeitungsvertrag) mit Anthropic abschließen wenn Pro-Plan oder höher
- Echte Kundendaten in Prompts oder Workspaces vermeiden, wenn das nicht sauber geregelt ist
- Anonymisierung als Standard ("Kunde A" statt Max Mustermann)

Mehr Details: Anthropic Trust Center und eigene Rechtsberatung wenn du große Mengen Personendaten verarbeitest.

:::tip[Ein-Minuten-Check]
Bevor du einen Workspace mit Claude verbindest: 60 Sekunden durch den Ordner schauen. Was läge da wenn ein Praktikant Zugriff bekäme? Wenn etwas dich nervös macht: rausnehmen, in einen Secret-Ordner verschieben, dann verbinden.
:::
