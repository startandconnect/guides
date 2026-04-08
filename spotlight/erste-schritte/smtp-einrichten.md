---
title: SMTP einrichten
order: 4
excerpt: Kontaktformulare und Benachrichtigungen aus deiner eigenen Mail senden
---

# SMTP einrichten

Damit Spotlight E-Mails aus deinem Namen verschickt (Kontaktformulare, Benachrichtigungen), brauchst du SMTP-Zugangsdaten.

## Wann du das brauchst

- **Kontaktformulare** auf deiner Website
- **Passwort-Zurücksetzen** E-Mails für Team-Mitglieder
- **System-Benachrichtigungen**

## SMTP-Einstellungen

Gehe zu **Einstellungen > SMTP** und trage ein:

| Feld | Beispiel |
|------|----------|
| Host | `smtp.ionos.de` |
| Port | `587` oder `465` |
| Secure | `TLS` (bei 587) oder `SSL` (bei 465) |
| Benutzername | `kontakt@meine-website.de` |
| Passwort | Dein Mail-Passwort |
| From-Name | z.B. "Meine Website" |
| From-E-Mail | `kontakt@meine-website.de` |

## Empfohlene Provider

- **IONOS** - smtp.ionos.de:587 (TLS)
- **Strato** - smtp.strato.de:587 (TLS)
- **Gmail** - smtp.gmail.com:587 (App-Passwort nötig)
- **SendGrid / Brevo / Postmark** - für höheres Mail-Volumen

> Brevo gibt es auch kostenlos mit 300 Mails/Tag - reicht für die meisten Websites.

## Testen

Klick nach dem Speichern auf **Test-E-Mail senden**. Du bekommst eine Test-Mail an die hinterlegte Adresse. Falls der Test fehlschlägt:

- **Authentifizierung fehlgeschlagen** - Passwort oder Benutzername falsch
- **Connection timeout** - Port oder Host falsch
- **TLS/SSL Fehler** - Secure-Modus prüfen (587=TLS, 465=SSL)

## Kontaktformular

Sobald SMTP eingerichtet ist, kannst du ein Kontaktformular einbauen. Im HTML-Override:

```html
<form action="/api/contact" method="POST">
  <input name="name" required>
  <input name="email" type="email" required>
  <textarea name="message" required></textarea>
  <button type="submit">Senden</button>
</form>
```

Die Nachricht kommt an die im SMTP hinterlegte From-Adresse.
