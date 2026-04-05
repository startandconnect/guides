---
title: System & Logs
order: 9
excerpt: System-Info, Datenbank, Cron Jobs und Logs einsehen
---

# System & Logs

Unter **Einstellungen > System** findest du technische Informationen und Diagnose-Tools für dein Portal.

## System-Info

Übersicht über deine Instanz:

- **Instanz-ID** - Eindeutige Kennung deines Portals
- **Version** - Aktuell installierte Nexus-Version
- **Uptime** - Laufzeit seit dem letzten Neustart
- **Node.js Version** - Runtime-Version
- **DB Version** - PostgreSQL-Version

## Datenbank

- **Name** - Name der Datenbank
- **Größe** - Aktueller Speicherverbrauch
- **Migrations-Status** - Zeigt an, ob alle Migrationen ausgeführt wurden

:::info[Hinweis]
Wenn der Migrations-Status nicht "Aktuell" anzeigt, wende dich an den Support. Fehlende Migrationen können zu Problemen führen.
:::

## Cron Jobs

Nexus führt regelmäßig geplante Aufgaben aus:

- **E-Mail-Warteschlange** - Versand ausstehender E-Mails
- **Webhook-Retry** - Wiederholung fehlgeschlagener Webhook-Zustellungen
- **Bereinigung** - Löschung abgelaufener Sessions und temporärer Dateien
- **Analytics** - Aggregation von Tracking-Daten

Für jeden Cron Job siehst du:

- Letzter Lauf und nächster geplanter Lauf
- Status (aktiv/inaktiv)
- Logs der letzten Ausführungen

Du kannst einzelne Cron Jobs aktivieren oder deaktivieren.

## Health Check

Prüfe den Status aller Systemkomponenten:

| Komponente | Prüft |
|---|---|
| **Datenbank** | Verbindung und Antwortzeit |
| **API** | Erreichbarkeit der Endpoints |
| **Services** | Status interner Dienste |
| **SMTP** | E-Mail-Verbindung |
| **Storage** | Dateispeicher-Zugriff |

## Hosting

- **Domain** - Aktuelle Domain deines Portals
- **SSL-Status** - Zertifikat gültig bis / Status
- **Server-Standort** - Rechenzentrum-Region

## Logs

Nexus protokolliert verschiedene Aktivitäten:

- **Audit Log** - Alle Admin-Aktionen (wer hat wann was geändert)
- **Security Log** - Login-Versuche, Passwort-Änderungen, verdächtige Aktivitäten
- **E-Mail Log** - Alle versendeten E-Mails mit Zustellstatus
- **Webhook Log** - Alle Webhook-Zustellungen und Responses
- **Error Log** - Systemfehler und Exceptions

Alle Logs können nach Zeitraum, Typ und Schweregrad gefiltert werden.

:::tip[Tipp]
Prüfe den Security Log regelmäßig auf ungewöhnliche Login-Versuche. Mehrere fehlgeschlagene Logins von der gleichen IP können auf einen Angriff hindeuten.
:::

## System-Tests

Teste einzelne Komponenten direkt aus den Einstellungen:

- **Test-E-Mail senden** - Sendet eine Test-E-Mail an deine Adresse
- **DB-Verbindung testen** - Prüft die Datenbankverbindung
- **Webhook testen** - Sendet einen Test-Payload an einen Webhook-Endpoint
