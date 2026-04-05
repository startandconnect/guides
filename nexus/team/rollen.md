---
title: Rollen & Berechtigungen
order: 2
excerpt: Vordefinierte Rollen, Custom Roles und Berechtigungsmatrix
---

# Rollen & Berechtigungen

Jedes Teammitglied braucht eine Rolle. Rollen bestimmen, welche Bereiche im Dashboard sichtbar und bearbeitbar sind. Nexus bringt sechs vordefinierte Rollen mit, und du kannst eigene erstellen.

## Vordefinierte Rollen

- **Owner** - Voller Zugriff auf alle Bereiche. Kann nicht entfernt werden und es gibt immer mindestens einen Owner pro Instanz.
- **Admin** - Fast vollständiger Zugriff. Kann Teammitglieder verwalten, aber keine Owner-Rechte ändern oder den Owner entfernen.
- **Member** - Standard-Rolle für Team-Mitarbeiter. Zugriff auf die meisten Bereiche, aber keine Team- oder Systemeinstellungen.
- **Support** - Speziell für den Kundensupport. Sieht Nachrichten, Kundendaten und Bestellungen, aber keine Einstellungen oder Analytics.
- **Seller** - Für Verkäufer und Partner. Zugriff auf eigene Produkte, Provisionen und Bestellungen. Mehr dazu unter [Verkäufer](/team/verkaeufer).
- **Accountant** - Für die Buchhaltung. Zugriff auf Rechnungen, Finanzdaten und Bestellungen, aber keine Produkt- oder Kundenverwaltung.

## Custom Roles

Die vordefinierten Rollen passen nicht? Erstelle eigene Rollen mit individuellen Berechtigungen:

1. Gehe zu **Einstellungen > Team > Rollen**
2. Klicke auf **Neue Rolle erstellen**
3. Vergib einen Namen (z.B. "Content Manager")
4. Aktiviere die gewünschten Berechtigungen per Checkbox
5. Speichere die Rolle

Custom Roles können jederzeit bearbeitet werden. Änderungen gelten sofort für alle Teammitglieder mit dieser Rolle.

:::info[Hinweis]
Custom Roles können nie mehr Rechte haben als die Admin-Rolle. Owner-Berechtigungen sind nicht übertragbar.
:::

## Berechtigungsmatrix - Admin-Bereich

| Modul | Owner | Admin | Member | Support | Seller | Accountant |
|-------|:-----:|:-----:|:------:|:-------:|:------:|:----------:|
| Dashboard | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| Produkte | ✓ | ✓ | ✓ | - | Eigene | - |
| Bestellungen | ✓ | ✓ | ✓ | ✓ | Eigene | ✓ |
| Kunden | ✓ | ✓ | ✓ | ✓ | - | - |
| Analytics | ✓ | ✓ | ✓ | - | Eigene | ✓ |
| Einstellungen | ✓ | ✓ | - | - | - | - |
| Team | ✓ | ✓ | - | - | - | - |
| Rechnungen | ✓ | ✓ | - | - | - | ✓ |
| Plugins | ✓ | ✓ | ✓ | - | - | - |

## Berechtigungsmatrix - Kundenportal-Module

| Modul | Owner | Admin | Member | Support | Seller | Accountant |
|-------|:-----:|:-----:|:------:|:-------:|:------:|:----------:|
| Käufe | ✓ | ✓ | ✓ | ✓ | Eigene | ✓ |
| Downloads | ✓ | ✓ | ✓ | ✓ | - | - |
| Events | ✓ | ✓ | ✓ | ✓ | - | - |
| Nachrichten | ✓ | ✓ | ✓ | ✓ | - | - |
| Abos | ✓ | ✓ | ✓ | ✓ | - | ✓ |
