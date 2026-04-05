---
title: Rollen & Berechtigungen
order: 2
excerpt: Komplette Berechtigungsmatrix für alle Rollen im Admin-Dashboard und Kundenportal
---

# Rollen & Berechtigungen

Nexus hat ein rollenbasiertes Berechtigungssystem. Jedes Teammitglied bekommt eine Rolle zugewiesen, die festlegt, auf welche Bereiche es Zugriff hat.

## Vordefinierte Rollen

| Rolle | Beschreibung |
|---|---|
| **Owner** | Vollzugriff auf alles, kann nicht eingeschränkt werden |
| **Admin** | Vollzugriff auf fast alles, kann keine System-Einstellungen ändern |
| **Member** | Zugriff auf operative Bereiche (Produkte, Bestellungen, Kunden) |
| **Support** | Zugriff auf Kunden und Nachrichten, kein Zugriff auf Finanzen |
| **Seller** | Zugriff auf Produkte und eigene Bestellungen |
| **Accountant** | Nur-Lesen-Zugriff auf Finanzbereiche (Bestellungen, Abonnements) |

## Admin-Berechtigungsmatrix

| Bereich | Owner | Admin | Member | Support | Seller | Accountant |
|---|---|---|---|---|---|---|
| Dashboard | Vollzugriff | Vollzugriff | Vollzugriff | Nur Lesen | Nur Lesen | Nur Lesen |
| Produkte | Vollzugriff | Vollzugriff | Vollzugriff | Kein Zugriff | Eigene | Kein Zugriff |
| Bestellungen | Vollzugriff | Vollzugriff | Vollzugriff | Nur Lesen | Eigene | Nur Lesen |
| Kunden | Vollzugriff | Vollzugriff | Vollzugriff | Vollzugriff | Kein Zugriff | Kein Zugriff |
| Abonnements | Vollzugriff | Vollzugriff | Vollzugriff | Nur Lesen | Kein Zugriff | Nur Lesen |
| Gutscheine | Vollzugriff | Vollzugriff | Vollzugriff | Kein Zugriff | Kein Zugriff | Kein Zugriff |
| Analytics | Vollzugriff | Vollzugriff | Nur Lesen | Kein Zugriff | Kein Zugriff | Nur Lesen |
| E-Mails | Vollzugriff | Vollzugriff | Vollzugriff | Kein Zugriff | Kein Zugriff | Kein Zugriff |
| Nachrichten | Vollzugriff | Vollzugriff | Vollzugriff | Vollzugriff | Kein Zugriff | Kein Zugriff |
| Events | Vollzugriff | Vollzugriff | Vollzugriff | Nur Lesen | Kein Zugriff | Kein Zugriff |
| Blog | Vollzugriff | Vollzugriff | Vollzugriff | Kein Zugriff | Kein Zugriff | Kein Zugriff |
| Newsletter | Vollzugriff | Vollzugriff | Vollzugriff | Kein Zugriff | Kein Zugriff | Kein Zugriff |
| Forms | Vollzugriff | Vollzugriff | Vollzugriff | Nur Lesen | Kein Zugriff | Kein Zugriff |
| Plugins | Vollzugriff | Vollzugriff | Kein Zugriff | Kein Zugriff | Kein Zugriff | Kein Zugriff |
| Einstellungen | Vollzugriff | Vollzugriff | Kein Zugriff | Kein Zugriff | Kein Zugriff | Kein Zugriff |
| Team | Vollzugriff | Vollzugriff | Kein Zugriff | Kein Zugriff | Kein Zugriff | Kein Zugriff |
| System | Vollzugriff | Kein Zugriff | Kein Zugriff | Kein Zugriff | Kein Zugriff | Kein Zugriff |

:::info[Hinweis]
"Eigene" bedeutet, dass der Nutzer nur Einträge sehen und bearbeiten kann, die er selbst erstellt hat.
:::

## Kundenportal-Berechtigungen

Die Rolle **Customer** hat Zugriff auf das Kundenportal mit folgenden Modulen:

| Modul | Customer | Beschreibung |
|---|---|---|
| Käufe | Vollzugriff | Eigene Bestellungen und Downloads einsehen |
| Downloads | Vollzugriff | Gekaufte digitale Produkte herunterladen |
| Abonnements | Vollzugriff | Eigene Abos verwalten und kündigen |
| Events | Vollzugriff | Registrierte Events und Tickets einsehen |
| Nachrichten | Vollzugriff | Support-Nachrichten senden und empfangen |
| Profil | Vollzugriff | Eigene Profildaten und Passwort ändern |
| Newsletter | Vollzugriff | Newsletter-Abonnement verwalten |

## Custom Roles

Neben den vordefinierten Rollen kannst du unter **Einstellungen > Zugriff** eigene Rollen erstellen. Dabei legst du für jeden Bereich individuell fest, welche Berechtigungsstufe gelten soll:

- **Vollzugriff** - Lesen, Erstellen, Bearbeiten, Löschen
- **Nur Lesen** - Nur Ansicht, keine Änderungen
- **Eigene** - Nur selbst erstellte Einträge sehen und bearbeiten
- **Kein Zugriff** - Bereich ist komplett ausgeblendet

:::tip[Tipp]
Erstelle Custom Roles für spezifische Anwendungsfälle, z.B. eine "Content Manager"-Rolle mit Zugriff auf Blog, Newsletter und Events, aber ohne Zugriff auf Finanzbereiche.
:::

:::warning[Wichtig]
Die Owner-Rolle kann nicht eingeschränkt oder gelöscht werden. Es muss immer mindestens einen Owner im System geben.
:::
