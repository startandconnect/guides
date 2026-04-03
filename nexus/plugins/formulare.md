---
title: Formulare
order: 5
excerpt: Drag & Drop Formular-Builder
---

# Formulare

Erstelle Formulare für Kontaktanfragen, Bewerbungen, Umfragen oder Lead-Erfassung. Drag & Drop Editor, automatische Lead-Erstellung und E-Mail-Benachrichtigungen.

## Formular erstellen

1. Gehe zu **Formulare** im Seitenmenü
2. Klicke auf **Neues Formular**
3. Ziehe Felder in den Editor

## Verfügbare Feldtypen

| Feldtyp | Beschreibung |
|---------|-------------|
| Text | Einzeilige Texteingabe |
| E-Mail | E-Mail-Adresse mit Validierung |
| Textbereich | Mehrzeilige Texteingabe |
| Zahl | Numerische Eingabe |
| Telefon | Telefonnummer |
| URL | Website-Adresse |
| Auswahl | Dropdown oder Multi-Select |
| Checkbox | Einzelne oder Gruppe von Checkboxen |
| Radio | Einfachauswahl |
| Datum | Datumspicker |
| Datei | Datei-Upload |
| Bewertung | Sterne-Rating |

Zusätzlich gibt es Layout-Elemente: Überschrift, Absatz, Trennlinie und Seitenumbruch.

## Einbetten

Formulare können auf verschiedene Arten genutzt werden:

- **Eigene Seite** - Jedes Formular hat eine eigene URL: `/forms/formular-slug`
- **Einbetten** - Als HTML-Override in eine beliebige Seite
- **API** - Einsendungen über die Public API

## Automatische Aktionen

Nach einer Einsendung passiert automatisch:

- **Kontakt anlegen** - Aus Vorname, Nachname und E-Mail wird ein Kontakt erstellt
- **Bestätigungs-E-Mail** - Optional an den Einsender
- **Benachrichtigung** - E-Mail an dein Team
- **Webhook** - HTTP-Request an eine externe URL

## Einsendungen verwalten

Unter **Formulare > [Formular] > Einsendungen** siehst du alle eingegangenen Daten:

- Filterbar nach Status (Neu, Gelesen, Archiviert)
- Exportierbar als CSV
- Einzelansicht mit allen Feldern

