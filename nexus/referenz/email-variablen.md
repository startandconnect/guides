---
title: E-Mail Template-Variablen
order: 1
excerpt: Alle verfügbaren Variablen für E-Mail Templates - gruppiert nach Kontext mit Beispielwerten
---

# E-Mail Template-Variablen

Nexus nutzt Handlebars als Template-Engine für E-Mails. Du kannst Variablen mit doppelten geschweiften Klammern einsetzen: `{{variablenname}}`. Hier findest du alle verfügbaren Variablen, gruppiert nach Kontext.

## Allgemeine Variablen

Diese Variablen stehen in jedem E-Mail Template zur Verfügung:

| Variable | Beschreibung | Beispielwert |
|---|---|---|
| `{{vorname}}` | Vorname des Empfängers | Max |
| `{{nachname}}` | Nachname des Empfängers | Mustermann |
| `{{email}}` | E-Mail-Adresse des Empfängers | max@beispiel.de |
| `{{portal_name}}` | Name deines Portals | Mein Portal |
| `{{portal_url}}` | URL deines Portals | https://meinportal.de |

## Bestellungen

Verfügbar in Bestellbestätigungen, Rechnungs-Mails und Zahlungserinnerungen:

| Variable | Beschreibung | Beispielwert |
|---|---|---|
| `{{bestellnummer}}` | Eindeutige Bestellnummer | ORD-2024-001 |
| `{{betrag}}` | Gesamtbetrag der Bestellung (formatiert) | 49,99 EUR |
| `{{produkt_name}}` | Name des bestellten Produkts | Online-Kurs SEO Basics |
| `{{datum}}` | Bestelldatum | 15.03.2024 |

## Abonnements

Verfügbar in Abo-Bestätigungen, Verlängerungen und Kündigungen:

| Variable | Beschreibung | Beispielwert |
|---|---|---|
| `{{abo_intervall}}` | Abrechnungsintervall | monatlich |
| `{{naechste_abrechnung}}` | Datum der nächsten Zahlung | 15.04.2024 |
| `{{bisher_gezahlt}}` | Gesamtbetrag bisheriger Zahlungen | 149,97 EUR |

## Events

Verfügbar in Event-Bestätigungen und Erinnerungen:

| Variable | Beschreibung | Beispielwert |
|---|---|---|
| `{{event.name}}` | Name des Events | Workshop: Content Marketing |
| `{{event.date}}` | Datum des Events | 20.04.2024 |
| `{{event.location}}` | Veranstaltungsort | Online via Zoom |
| `{{event.startTime}}` | Startzeit | 10:00 |
| `{{event.endTime}}` | Endzeit | 12:00 |
| `{{attendanceType}}` | Teilnahmeart (online/vor Ort) | online |

## Hosting

Verfügbar in Hosting-bezogenen Benachrichtigungen:

| Variable | Beschreibung | Beispielwert |
|---|---|---|
| `{{hosting.url}}` | URL der Hosting-Instanz | https://app.beispiel.de |
| `{{hosting.domain}}` | Domain der Instanz | app.beispiel.de |
| `{{hosting.status}}` | Aktueller Status | active |

## Konditionale Blöcke

Mit konditionalen Blöcken kannst du Inhalte nur anzeigen, wenn eine bestimmte Bedingung erfüllt ist. Nexus unterstützt dafür eine eigene Syntax:

```
{variable:show}
Dieser Text wird nur angezeigt, wenn die Variable einen Wert hat.
{/variable:show}
```

### Beispiel: Online-Teilnehmer

```
{isOnlineParticipant:show}
Dein Zoom-Link: https://zoom.us/j/123456789
Bitte logge dich 5 Minuten vor Beginn ein.
{/isOnlineParticipant:show}
```

### Beispiel: Vor-Ort-Teilnehmer

```
{isOnsiteParticipant:show}
Adresse: Musterstraße 1, 12345 Berlin
Bitte sei 15 Minuten vor Beginn da.
{/isOnsiteParticipant:show}
```

## Handlebars-Syntax

Nexus verwendet Handlebars als Template-Engine. Neben einfachen Variablen stehen dir diese Konstrukte zur Verfügung:

### Bedingte Ausgabe

```handlebars
{{#if variable}}
Dieser Text wird angezeigt, wenn die Variable existiert und nicht leer ist.
{{/if}}
```

```handlebars
{{#if variable}}
Text wenn vorhanden
{{else}}
Fallback-Text
{{/if}}
```

### Schleifen

```handlebars
{{#each items}}
- {{this.name}}: {{this.preis}}
{{/each}}
```

:::tip[Tipp]
Du kannst Handlebars und konditionale Blöcke kombinieren. Handlebars eignet sich besonders gut für Listen (z.B. Bestellpositionen), während konditionale Blöcke ideal für einfache Ja/Nein-Entscheidungen sind.
:::

### Beispiel: Komplettes Template

```handlebars
Hallo {{vorname}},

vielen Dank für deine Bestellung ({{bestellnummer}}).

Bestellte Produkte:
{{#each items}}
- {{this.name}} - {{this.preis}}
{{/each}}

Gesamtbetrag: {{betrag}}

{isDigitalProduct:show}
Du findest deine Downloads in deinem Kundenportal unter:
{{portal_url}}/downloads
{/isDigitalProduct:show}

Viele Grüße,
{{portal_name}}
```

:::info[Hinweis]
Template-Variablen werden beim Versand automatisch ersetzt. In der Vorschau im Dashboard siehst du Beispielwerte, damit du das Layout prüfen kannst.
:::
