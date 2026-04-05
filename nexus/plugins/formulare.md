---
title: Formulare
order: 5
excerpt: Drag & Drop Formular-Builder mit Lead-Erstellung und Public API
---

# Formulare

Erstelle Formulare für Kontaktanfragen, Bewerbungen, Umfragen oder Lead-Erfassung. Mit Drag & Drop Editor, automatischer Lead-Erstellung, E-Mail-Benachrichtigungen und Public API.

## Formular erstellen

1. Gehe zu **Formulare** im Seitenmenü
2. Klicke auf **Neues Formular**
3. Vergib einen Namen und einen **Slug** (URL-Pfad, z.B. `kontakt`)
4. Ziehe Felder per Drag & Drop in den Editor
5. Konfiguriere jedes Feld (Label, Pflichtfeld, Platzhalter)
6. Klicke auf **Veröffentlichen**

Mit **Publish/Unpublish** kannst du Formulare jederzeit aktivieren oder deaktivieren. Unveröffentlichte Formulare sind nicht mehr über die URL erreichbar.

## Feldtypen

Nexus bietet über 13 Feldtypen:

| Feldtyp | Beschreibung |
|---------|-------------|
| **Text** | Einzeilige Texteingabe |
| **E-Mail** | E-Mail-Adresse mit Validierung |
| **Textarea** | Mehrzeilige Texteingabe |
| **Number** | Numerische Eingabe |
| **Phone** | Telefonnummer |
| **URL** | Website-Adresse |
| **Select** | Dropdown oder Multi-Select |
| **Checkbox** | Einzelne oder Gruppe von Checkboxen |
| **Radio** | Einfachauswahl |
| **Date** | Datumspicker |
| **File Upload** | Datei-Upload (Bilder, PDFs, etc.) |
| **Rating** | Sterne-Bewertung |
| **Hidden** | Verstecktes Feld (für Tracking-Parameter, UTM-Tags, etc.) |

Zusätzlich gibt es Layout-Elemente: Überschrift, Absatz, Trennlinie und Seitenumbruch.

## Einreichungen verwalten

Unter **Formulare > [Formular] > Einsendungen** siehst du alle eingegangenen Daten:

- **Dashboard-Übersicht** - Alle Einsendungen auf einen Blick mit Zeitstempel
- **Einzelansicht** - Alle ausgefüllten Felder pro Submission
- **Export** - Einsendungen als CSV exportieren

## Automatische Lead-Erstellung

Nexus erkennt automatisch E-Mail-Felder in deinem Formular:

1. Die E-Mail-Adresse wird als Lead-Kontakt angelegt
2. Vorname und Nachname werden aus einem Namensfeld gesplittet (z.B. "Max Mustermann" wird zu Vorname "Max" und Nachname "Mustermann")
3. Der Lead erscheint in deiner Kontaktliste mit Quelle "Formular"

So baust du automatisch deine Kontaktdatenbank auf.

## E-Mail Templates

Du kannst pro Formular eigene E-Mail Templates verwenden:

- **Bestätigungsmail an Absender** - Automatische Eingangsbestätigung nach dem Absenden. Nutze `templateSlug` um ein Custom Template zuzuweisen.
- **Benachrichtigungsmail an Admin** - Informiert dein Team über neue Einsendungen. Konfiguriere das `recipients` Array um mehrere Empfänger festzulegen.

## Cal.com Integration

Formulare können mit Cal.com verknüpft werden:

- Nach dem Absenden wird ein **prefilled Buchungslink** generiert
- Name, E-Mail und Notizen aus dem Formular werden automatisch an Cal.com übergeben
- Der Nutzer wird direkt zur Terminbuchung weitergeleitet

:::tip[Tipp]
Nutze die Cal.com Integration für Beratungsanfragen. Der Interessent füllt das Formular aus und kann direkt im Anschluss einen Termin buchen - ohne manuellen Zwischenschritt.
:::

## Public API

Formulare können auch programmatisch befüllt werden:

```
POST /api/plugins/forms/public/forms/{slug}/submit
Content-Type: application/json

{
  "data": {
    "name": "Max Mustermann",
    "email": "max@beispiel.de",
    "nachricht": "Hallo, ich habe eine Frage..."
  }
}
```

Die Feld-Keys im `data` Objekt müssen den Feldnamen in deinem Formular entsprechen.

:::warning[Wichtig]
Die Public API hat ein **Rate Limit von 5 Anfragen pro Minute pro IP**. Das schützt vor Spam und Missbrauch.
:::

## Webhooks

Nach jeder Einsendung kann Nexus einen HTTP-Request an eine externe URL senden:

1. Konfiguriere die Webhook-URL in den Formular-Einstellungen
2. Nexus sendet einen POST-Request mit allen Formulardaten als JSON
3. Nutze das für Integrationen mit Zapier, Make, n8n oder eigenen Systemen
