---
title: E-Mail & SMTP
order: 1
excerpt: SMTP konfigurieren, Templates anpassen und E-Mail-Versand überwachen
---

# E-Mail & SMTP

Nexus versendet System-E-Mails wie Bestellbestätigungen, Passwort-Resets und Willkommensnachrichten. Dafür brauchst du einen SMTP-Anbieter.

## SMTP konfigurieren

Unter **Einstellungen > E-Mail** trägst du deine SMTP-Zugangsdaten ein:

- **Host** - z.B. `smtp-relay.brevo.com` oder `smtp.eu.mailgun.org`
- **Port** - Standard: `587` (TLS) oder `465` (SSL)
- **Benutzername** - Dein SMTP-Benutzername
- **Passwort** - Dein SMTP-Passwort/API-Key
- **Verschlüsselung** - TLS (empfohlen) oder SSL

:::tip[Tipp]
Mailgun EU (`smtp.eu.mailgun.org`) und Brevo sind DSGVO-konforme Anbieter mit Servern in der EU. Für die meisten Portale reichen die kostenlosen Kontingente.
:::

## Absender konfigurieren

- **Absender-E-Mail** - Die Adresse, von der E-Mails verschickt werden (z.B. `noreply@deinportal.de`)
- **Absender-Name** - Der angezeigte Name (z.B. dein Portalname)

Stelle sicher, dass die Absender-Domain in deinem SMTP-Anbieter verifiziert ist (SPF, DKIM, DMARC).

## System E-Mail Templates

Nexus enthält vorkonfigurierte Templates für alle System-E-Mails:

| Template | Auslöser |
|---|---|
| Kaufbestätigung | Nach erfolgreichem Kauf |
| Willkommens-E-Mail | Bei Registrierung |
| Passwort-Reset | Passwort zurücksetzen angefordert |
| E-Mail-Verifizierung | Neue E-Mail-Adresse bestätigen |
| Formular-Bestätigung | Nach Formular-Einsendung |
| Einladung | Team-Mitglied eingeladen |

Jedes Template kann im visuellen Editor angepasst werden.

## Template-Variablen

Templates nutzen Handlebars-Syntax. Verfügbare Variablen:

```handlebars
{{vorname}}         - Vorname des Empfängers
{{nachname}}        - Nachname
{{email}}           - E-Mail-Adresse
{{portal_name}}     - Name deiner Plattform
{{portal_url}}      - URL deiner Plattform
{{bestellnummer}}   - Nur bei Bestellungen
{{betrag}}          - Nur bei Bestellungen
```

### Konditionale Blöcke

Du kannst Inhalte abhängig von Variablen ein- oder ausblenden:

```handlebars
{{#if bestellnummer}}
  Deine Bestellnummer: {{bestellnummer}}
{{/if}}
```

:::warning[Wichtig]
Änderungen an System-Templates werden sofort aktiv. Nutze die Vorschau-Funktion, bevor du speicherst.
:::

## E-Mail Log

Unter **E-Mail Log** siehst du alle versendeten E-Mails mit Status (zugestellt, fehlgeschlagen, ausstehend). Filtere nach Zeitraum, Empfänger oder Template.

## Bounce-Handling

Fehlgeschlagene Zustellungen werden automatisch protokolliert. Bei wiederholten Bounces (Hard Bounces) wird die Adresse als ungültig markiert und erhält keine weiteren E-Mails.
