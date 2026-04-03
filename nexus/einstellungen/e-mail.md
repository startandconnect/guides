---
title: E-Mail & SMTP
order: 1
excerpt: E-Mail-Versand einrichten
---

# E-Mail & SMTP

Nexus versendet verschiedene E-Mails: Bestellbestätigungen, Passwort-Resets, Newsletter und mehr. Dafür brauchst du einen SMTP-Anbieter.

## SMTP einrichten

1. Gehe zu **Einstellungen > E-Mail**
2. Trage deine SMTP-Daten ein:
   - **Host** - z.B. `smtp-relay.brevo.com`
   - **Port** - z.B. `587`
   - **Benutzername** - Dein SMTP-Benutzername
   - **Passwort** - Dein SMTP-Passwort
3. Teste die Verbindung mit dem **Test senden** Button

## E-Mail Templates

Unter **E-Mails** verwaltest du alle Templates:

- **Bestellbestätigung** - Nach jedem Kauf
- **Willkommens-E-Mail** - Bei Registrierung
- **Passwort-Reset** - Link zum Zurücksetzen
- **Newsletter** - Für Kampagnen
- **Formular-Bestätigung** - Nach Formular-Einsendung

Jedes Template hat einen visuellen Editor mit Variablen:

```
{{vorname}}         - Vorname des Empfängers
{{nachname}}        - Nachname
{{email}}           - E-Mail-Adresse
{{portal_name}}     - Name deiner Plattform
{{portal_url}}      - URL deiner Plattform
{{bestellnummer}}   - Nur bei Bestellungen
{{betrag}}          - Nur bei Bestellungen
```

:::danger[Achtung]
Änderungen an System-Templates (Bestellbestätigung, Passwort-Reset) werden sofort aktiv. Teste sie vorher mit der Vorschau-Funktion.
:::
