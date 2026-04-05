---
title: Zugriff & Rollen
order: 7
excerpt: Rollen, Berechtigungen und Team-Verwaltung konfigurieren
---

# Zugriff & Rollen

Unter **Einstellungen > Zugriff** verwaltest du Rollen, Berechtigungen und Team-Mitglieder.

## Rollen-Übersicht

Nexus hat folgende Standard-Rollen:

| Rolle | Beschreibung |
|---|---|
| **Owner** | Vollzugriff, kann Portal löschen und Rollen verwalten |
| **Admin** | Vollzugriff auf alle Bereiche, kann keine Owner-Rechte ändern |
| **Member** | Team-Mitglied mit eingeschränktem Zugriff |
| **Customer** | Registrierter Kunde mit Zugang zum Kundenportal |
| **Seller** | Kann eigene Produkte erstellen und verwalten |
| **Support** | Zugriff auf Nachrichten und Kundenanfragen |
| **Accountant** | Zugriff auf Bestellungen, Rechnungen und Finanzdaten |

## Berechtigungsmatrix

Berechtigungen sind in zwei Bereiche unterteilt:

### Admin-Module

Steuert, welche Manage-Bereiche im Admin-Dashboard sichtbar sind:

- Produkte, Bestellungen, Kunden, Nachrichten
- Analytics, E-Mails, Formulare, Blog
- Einstellungen, System

### Portal-Module

Steuert, welche Bereiche im Kundenportal sichtbar sind:

- Mein Bereich, Bestellungen, Nachrichten
- Profil, Downloads, Kurse

:::info[Hinweis]
Owner und Admin haben immer Zugriff auf alle Module. Einschränkungen gelten nur für andere Rollen.
:::

## Custom Roles

Erstelle eigene Rollen für spezielle Anforderungen:

1. Gehe zu **Einstellungen > Zugriff > Rollen**
2. Klicke auf **Neue Rolle**
3. Vergib einen Namen (z.B. "Content Manager")
4. Wähle die gewünschten Admin- und Portal-Module aus
5. Speichern

## Team einladen

So fügst du neue Team-Mitglieder hinzu:

1. Gehe zu **Einstellungen > Zugriff > Team**
2. Klicke auf **Einladen**
3. Trage die E-Mail-Adresse ein
4. Wähle eine Rolle
5. Die Person erhält eine Einladungs-E-Mail mit Registrierungslink

:::tip[Tipp]
Vergib nur die minimal nötigen Berechtigungen. Ein Content Manager braucht keinen Zugriff auf Finanzdaten, ein Support-Mitarbeiter keine Produktverwaltung.
:::

## Berechtigungen pro User überschreiben

Du kannst für einzelne Nutzer die Rollen-Berechtigungen granular überschreiben:

1. Öffne das Profil des Nutzers
2. Gehe zu **Berechtigungen**
3. Aktiviere oder deaktiviere einzelne Module

Überschreibungen gelten nur für diesen Nutzer und haben Vorrang vor der Rollen-Konfiguration.
