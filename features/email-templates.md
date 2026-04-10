---
title: E-Mail Templates
order: 2
excerpt: E-Mail Templates erstellen und verwalten
---

# E-Mail Templates

Nexus bietet ein visuelles Template-System fuer alle E-Mails die dein Portal versendet. Du findest sie unter **E-Mails** in der Seitenleiste.

## Template-Typen

### Bestellungen und Zahlungen

| Template | Beschreibung | Automatisch |
|----------|-------------|-------------|
| Bestellbestaetigung | Wird nach erfolgreicher Zahlung an den Kunden gesendet | Ja |
| Erstattung bestaetigt | Wird bei einer Rueckerstattung an den Kunden gesendet | Ja |
| Rechnungskorrektur | Wird nach einer Rechnungskorrektur gesendet | Ja |
| Zahlung fehlgeschlagen (Admin) | Interne Benachrichtigung wenn eine Zahlung fehlschlaegt oder zurueckgebucht wird | Ja, wenn aktiviert |
| Zahlung fehlgeschlagen (Kunde) | Info-E-Mail an den Kunden bei fehlgeschlagener Zahlung | Ja, wenn aktiviert |
| Warenkorbabbrecher | Wird gesendet wenn ein Checkout abgebrochen wird | Ja |

### Authentifizierung und Sicherheit

| Template | Beschreibung | Automatisch |
|----------|-------------|-------------|
| Willkommens-E-Mail | Fuer neue Benutzer/Kunden | Ja |
| E-Mail-Verifizierung | Bestaetigung der E-Mail-Adresse | Ja |
| Passwort zuruecksetzen | Link zum Zuruecksetzen des Passworts | Ja |
| Passwort festlegen | Fuer neue Nutzer ohne Passwort (z.B. nach Checkout) | Ja |
| Passwort geaendert | Bestaetigung nach Passwortaenderung | Ja |
| Team-Einladung | Einladung fuer Teammitglieder | Ja |

### Abonnements

| Template | Beschreibung | Automatisch |
|----------|-------------|-------------|
| Abo verlaengert | Bestaetigung bei automatischer Verlaengerung | Ja |
| Abo gekuendigt | Bestaetigung nach Kuendigung | Ja |

### Newsletter und Marketing

| Template | Beschreibung | Automatisch |
|----------|-------------|-------------|
| Newsletter bestaetigen | Double-Opt-In Bestaetigungsmail | Ja |
| Newsletter Erinnerung | Erinnerung an unbestaetigte Anmeldung | Ja |
| Newsletter bestaetigt | Bestaetigung nach Double-Opt-In | Ja |
| Marketing-Abmeldung bestaetigt | Bestaetigung der Abmeldung | Ja |

## Template bearbeiten

Templates werden mit einem visuellen Editor bearbeitet. Du kannst:

- **Texte** anpassen und formatieren
- **Buttons** einfuegen (z.B. Call-to-Action Links)
- **Variablen** nutzen die automatisch ersetzt werden
- **Betreff** und **Preheader** individuell setzen
- Templates per **Vorschau** und **Test-E-Mail** pruefen

:::danger[Achtung]
Aenderungen an System-Templates werden sofort aktiv. Teste sie vorher mit der Vorschau-Funktion oder sende eine Test-E-Mail an dich selbst.
:::

## Variablen

Verfuegbare Variablen haengen vom Template-Typ ab. Im Editor siehst du alle verfuegbaren Variablen fuer das jeweilige Template. Grundsaetzlich verfuegbar:

| Variable | Beschreibung |
|----------|-------------|
| `{customer.firstName}` | Vorname des Empfaengers |
| `{customer.lastName}` | Nachname des Empfaengers |
| `{customer.email}` | E-Mail-Adresse |
| `{portal.name}` | Name deines Portals |
| `{portal.url}` | URL deines Portals |
| `{order.number}` | Bestellnummer (nur bei Bestellungen) |
| `{order.total}` | Gesamtbetrag (nur bei Bestellungen) |

## Fehlgeschlagene Zahlungen

Die beiden Templates **Zahlung fehlgeschlagen (Admin)** und **Zahlung fehlgeschlagen (Kunde)** werden nur versendet wenn du die Benachrichtigungen in den Einstellungen aktiviert hast.

So aktivierst du sie:

1. Gehe zu **Einstellungen** > **Zahlung** > **Stripe**
2. Scrolle zum Abschnitt **Fehlgeschlagene Zahlungen**
3. Aktiviere **Admin benachrichtigen** und/oder **Kunden benachrichtigen**
4. Optional: Trage eine eigene E-Mail-Adresse ein (sonst wird die Support-E-Mail des Portals verwendet)

Die E-Mails werden automatisch gesendet wenn eine Zahlung fehlschlaegt, z.B. bei einer SEPA-Rueckbuchung oder abgelehnten Kreditkarte.
