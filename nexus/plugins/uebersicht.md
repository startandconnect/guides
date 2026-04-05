---
title: Plugin-Übersicht
order: 1
excerpt: Alle verfügbaren Plugins und wie du sie im Marketplace findest und aktivierst
---

# Plugin-Übersicht

Nexus hat ein modulares Plugin-System. Jedes Plugin erweitert deine Plattform um eigene Admin-Seiten, API-Endpoints und Datenbank-Tabellen. Aktiviere nur die Features die du brauchst - alle Plugins sind in deinem Nexus-Abo enthalten.

## Marketplace

Im Marketplace findest du alle verfügbaren Plugins:

1. Gehe zu **Einstellungen > Plugins**
2. Du siehst alle Plugins mit Beschreibung und Status
3. Klicke auf ein Plugin um Details zu sehen
4. Klicke auf **Installieren** bzw. **Aktivieren**

:::info[Hinweis]
Manche Plugins sind als **Private Plugins** markiert. Diese sind nur für bestimmte Kunden verfügbar und erscheinen nicht im öffentlichen Marketplace.
:::

## Plugins aktivieren und deaktivieren

Nach der Installation kannst du ein Plugin jederzeit aktivieren oder deaktivieren:

1. Gehe zu **Einstellungen > Plugins**
2. Klicke auf den Schalter neben dem Plugin
3. Deaktivierte Plugins werden nicht gelöscht - deine Daten bleiben erhalten

Beim Aktivieren legt das Plugin automatisch seine Datenbank-Tabellen an und registriert seine API-Endpoints.

## ZIP-Installation

Neben dem Marketplace kannst du Plugins auch manuell als ZIP-Datei installieren:

1. Gehe zu **Einstellungen > Plugins**
2. Klicke auf **Plugin hochladen**
3. Wähle die ZIP-Datei aus
4. Das Plugin wird installiert und ist sofort verfügbar

Das ist nützlich für Custom-Plugins oder Vorabversionen.

## Plugin-Updates

Wenn ein Plugin-Update verfügbar ist, siehst du einen Hinweis in den Plugin-Einstellungen. Updates werden über den Marketplace eingespielt:

1. Gehe zu **Einstellungen > Plugins**
2. Plugins mit verfügbarem Update zeigen einen **Update**-Button
3. Klicke auf **Update** - das Plugin wird aktualisiert, deine Daten bleiben erhalten

:::warning[Wichtig]
Bei Plugins die per ZIP installiert wurden, musst du das Update ebenfalls als ZIP-Datei hochladen. Der Marketplace aktualisiert nur Plugins die darüber installiert wurden.
:::

## Verfügbare Plugins

| Plugin | Beschreibung |
|--------|-------------|
| **Blog** | Artikel, Kategorien, Tags, RSS-Feed. Content-Marketing direkt in Nexus |
| **Events** | Veranstaltungen mit Buchung, Check-in und Teilnehmerverwaltung |
| **Newsletter** | E-Mail-Kampagnen, Sequenzen, Segmente und Listen |
| **Formulare** | Drag & Drop Formular-Builder mit automatischer Lead-Erstellung |
| **Reviews** | Kundenbewertungen mit Moderation und Sterne-Rating |
| **Wunschliste** | Kunden können Produkte merken und direkt von der Liste kaufen |
| **Chatbot** | KI-gestützter Chatbot der Kundenfragen automatisch beantwortet |
| **Affiliate** | Partner-Programm mit Provisionsabrechnung und Tracking |
| **Brevo** | Kontakt-Sync und Listen-Zuordnung mit Brevo (ehemals Sendinblue) |
| **Circle** | Community-Integration mit automatischem Member-Sync |
| **Google Ads** | DSGVO-konformes Server-Side Conversion Tracking |
| **Guide** | Produktdokumentation aus Git-Repositories als Wissensdatenbank |

## Was Plugins mitbringen

Jedes Plugin ist ein eigenständiges Modul mit:

- **Eigene Admin-Seiten** - Erscheinen im Seitenmenü nach Aktivierung
- **Eigene API-Endpoints** - Unter `/api/plugins/{plugin-name}/...`
- **Eigene Datenbank-Tabellen** - Werden beim Aktivieren automatisch erstellt
- **Eigene Einstellungen** - Konfigurierbar unter **Einstellungen > Plugins > [Plugin-Name]**

:::tip[Tipp]
Du kannst Plugins jederzeit testen. Aktiviere ein Plugin, probiere es aus, und deaktiviere es wieder wenn du es nicht brauchst. Deine Daten bleiben auch bei Deaktivierung erhalten.
:::
