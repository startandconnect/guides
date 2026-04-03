---
title: E-Mail Templates
order: 2
excerpt: E-Mail Templates erstellen und verwalten
---

# E-Mail Templates

Nexus bietet ein visuelles Template-System für alle E-Mails die dein Portal versendet.

## Template-Typen

| Typ | Beschreibung |
|-----|-------------|
| Bestellbestätigung | Wird nach einer Bestellung versendet |
| Willkommens-E-Mail | Für neue Benutzer/Kunden |
| Passwort-Reset | Link zum Zurücksetzen des Passworts |
| Newsletter | Für Newsletter-Kampagnen |
| Formular-Bestätigung | Nach Formular-Einsendung |

## Template bearbeiten

Templates werden mit einem visuellen Editor bearbeitet. Du kannst:

- **Texte** anpassen
- **Bilder** einfügen
- **Variablen** nutzen (z.B. `{{name}}`, `{{bestellnummer}}`)
- **Farben** an dein Branding anpassen

:::danger[Achtung]
Änderungen an System-Templates (Bestellbestätigung, Passwort-Reset) werden sofort aktiv. Teste sie vorher mit der Vorschau-Funktion.
:::

## Variablen

Verfügbare Variablen hängen vom Template-Typ ab:

```
{{vorname}}        - Vorname des Empfängers
{{nachname}}       - Nachname des Empfängers
{{email}}          - E-Mail-Adresse
{{portal_name}}    - Name deines Portals
{{portal_url}}     - URL deines Portals
{{bestellnummer}}  - Nur bei Bestellungen
{{betrag}}         - Nur bei Bestellungen
```

