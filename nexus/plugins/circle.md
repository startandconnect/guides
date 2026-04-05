---
title: Circle
order: 11
excerpt: Community-Integration mit automatischem Member-Sync nach Produktkauf
---

# Circle

Verbinde deine Nexus-Plattform mit Circle und gewähre Käufern automatisch Zugang zu deiner Community. Kein manuelles Einladen mehr - Nexus übernimmt den Member-Sync.

## API-Credentials konfigurieren

1. Gehe zu **Einstellungen > Plugins > Circle**
2. Trage deine Circle API-Credentials ein (API Token aus den Circle Admin Settings)
3. Speichere die Einstellungen
4. Nexus verbindet sich mit deiner Circle Community

## Member-Sync

Nach der Konfiguration synchronisiert Nexus Käufer automatisch mit Circle:

1. Kunde kauft ein Produkt in Nexus
2. Nexus prüft ob für das Produkt eine Circle-Zuordnung hinterlegt ist
3. Der Kunde wird automatisch als Member in Circle eingeladen
4. Der Kunde erhält eine Einladungs-E-Mail von Circle

Der gesamte Prozess läuft automatisch im Hintergrund.

## Pro Produkt konfigurieren

Für jedes Nexus-Produkt kannst du individuell festlegen:

- **Circle Space** - In welchen Space der Käufer hinzugefügt wird
- **Rolle** - Welche Rolle der Käufer in Circle erhält (Member, Moderator, etc.)

So erhalten Käufer verschiedener Produkte Zugang zu unterschiedlichen Bereichen deiner Community.

:::tip[Tipp]
Erstelle in Circle für jedes Produkt oder jede Kurskohorte einen eigenen Space. So können sich Teilnehmer untereinander austauschen ohne andere Bereiche zu sehen.
:::

## Community-Link in E-Mails

Nach erfolgreicher Zuordnung kannst du in deinen Bestätigungs-E-Mails einen direkten Link zur Community einbauen:

- Nutze die E-Mail-Templates in Nexus
- Füge den Circle Community-Link als Button oder Textlink ein
- Der Kunde kommt direkt in den richtigen Space

## Automatische Einladungen

Nexus versendet die Circle-Einladung automatisch nach dem Kauf:

- Neue Mitglieder erhalten eine E-Mail von Circle mit Einladungslink
- Bestehende Circle-Mitglieder werden dem neuen Space automatisch hinzugefügt
- Es gibt keine Duplikate - Nexus prüft ob der Kontakt bereits in Circle existiert

## Membership-Verwaltung

Unter **Circle** im Seitenmenü siehst du:

- **Status** - Welche Kunden erfolgreich synchronisiert wurden
- **Sync-Logs** - Detailliertes Protokoll aller Sync-Vorgänge (Erfolg, Fehler, Wiederholungen)

:::info[Hinweis]
Bei Stornierungen wird der Circle-Zugang nicht automatisch entzogen. Du kannst das manuell in Circle verwalten oder einen Automation-Workflow einrichten.
:::
