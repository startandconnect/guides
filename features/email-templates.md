---
title: E-Mail Templates
order: 2
excerpt: E-Mail Templates erstellen und verwalten
---

# E-Mail Templates

Nexus bietet ein visuelles Template-System fuer alle E-Mails die dein Portal versendet.

## Template-Typen

| Typ | Beschreibung |
|-----|-------------|
| Bestellbestaetigung | Wird nach einer Bestellung versendet |
| Willkommens-E-Mail | Fuer neue Benutzer/Kunden |
| Passwort-Reset | Link zum Zuruecksetzen des Passworts |
| Newsletter | Fuer Newsletter-Kampagnen |
| Formular-Bestaetigung | Nach Formular-Einsendung |

## Template bearbeiten

Templates werden mit einem visuellen Editor bearbeitet. Du kannst:

- **Texte** anpassen
- **Bilder** einfuegen
- **Variablen** nutzen (z.B. `{{name}}`, `{{bestellnummer}}`)
- **Farben** an dein Branding anpassen

:::danger[Achtung]
Aenderungen an System-Templates (Bestellbestaetigung, Passwort-Reset) werden sofort aktiv. Teste sie vorher mit der Vorschau-Funktion.
:::

## Variablen

Verfuegbare Variablen haengen vom Template-Typ ab:

```
{{vorname}}        - Vorname des Empfaengers
{{nachname}}       - Nachname des Empfaengers
{{email}}          - E-Mail-Adresse
{{portal_name}}    - Name deines Portals
{{portal_url}}     - URL deines Portals
{{bestellnummer}}  - Nur bei Bestellungen
{{betrag}}         - Nur bei Bestellungen
```
