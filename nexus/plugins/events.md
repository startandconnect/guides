---
title: Events
order: 3
excerpt: Veranstaltungen mit Buchung, Ticketing und Teilnehmerverwaltung
---

# Events

Organisiere Veranstaltungen jeder Art - von eintägigen Workshops über mehrtägige Seminare bis hin zu Ausbildungsreihen mit mehreren Blöcken. Mit Buchung, Ticketing, Check-in und automatischen E-Mails.

## Event erstellen

1. Gehe zu **Events** im Seitenmenü
2. Klicke auf **Neues Event**
3. Fülle die Details aus: Titel, Beschreibung, Typ, Datum und Uhrzeit
4. Setze Ort, Kapazität und Preis
5. Konfiguriere die Teilnahme-Art und Delivery Actions
6. Veröffentliche das Event

## Event-Typen

Nexus unterstützt vier Event-Typen:

### Eintägig

Ein klassisches Event an einem Tag. Du setzt `startsAt` und `endsAt` am selben Tag, z.B. ein Workshop von 9:00 bis 17:00.

### Mehrtägig

Ein durchgehender Zeitraum über mehrere Tage. Setze `startsAt` auf den ersten und `endsAt` auf den letzten Tag, z.B. eine Konferenz von Montag bis Freitag.

### Einzeltermine

Ein Parent-Event mit einer manuellen Liste einzelner Termine. Ideal für Kursreihen mit unregelmäßigen Terminen. Du erstellst das Parent-Event und fügst dann einzelne Termine (Occurrences) hinzu, z.B. ein Abendkurs jeden Dienstag im März.

### Block-Events

Ein Parent-Event mit mehrtägigen Blöcken. Perfekt für Ausbildungsreihen, z.B. "Ausbildung zum Coach - Teil I (Mo-Fr)" und "Teil II (Mo-Fr)" mit Wochen dazwischen.

## Teilnahme-Arten

Jedes Event hat eine Attendance Type:

| Typ | Beschreibung |
|-----|-------------|
| **PHYSICAL** | Vor-Ort-Event mit Adresse |
| **ONLINE** | Online-Event mit Video-Link (Zoom, Google Meet, etc.) |
| **HYBRID** | Vor Ort und Online gleichzeitig |

## Teilnehmerverwaltung

### Kapazitäten

Setze eine maximale Teilnehmerzahl pro Event. Ist die Kapazität erreicht, landen weitere Buchungen automatisch auf der **Warteliste**.

### Ticketing

Pro Registrierung können mehrere Tickets gebucht werden. So kann eine Person z.B. drei Plätze für Kollegen reservieren.

### Check-in

Für Vor-Ort-Events bietet Nexus ein Check-in System. Markiere Teilnehmer beim Eintreffen als eingecheckt - entweder manuell in der Teilnehmerliste oder per QR-Code.

### Export und Deduplizierung

- **CSV-Export** - Exportiere die Teilnehmerliste als CSV
- **Deduplizierung** - Bei Block-Events mit mehreren Terminen wird jeder Teilnehmer nur einmal gezählt, auch wenn er an mehreren Blöcken teilnimmt

## Delivery Actions

Nexus verschickt automatisch drei E-Mails pro Event:

1. **Buchungsbestätigung** - Sofort nach der Buchung mit allen Event-Details
2. **Seminarinfos** - 2 Wochen vor dem Event mit praktischen Informationen
3. **Erinnerung** - 1 Tag vor dem Event als letzte Erinnerung

### eventOccurrence

Bei Events mit mehreren Terminen steuerst du mit `eventOccurrence`, wann welche E-Mail gesendet wird:

| Wert | Beschreibung |
|------|-------------|
| **FIRST** | Nur beim ersten Termin |
| **ALL** | Bei jedem Termin |
| **LAST** | Nur beim letzten Termin |

### Konditionale Blöcke

In den E-Mail-Templates kannst du konditionale Blöcke für Online-Teilnehmer verwenden. So erhält ein Online-Teilnehmer den Zoom-Link, während der Vor-Ort-Teilnehmer die Anfahrtsbeschreibung bekommt.

:::tip[Tipp]
Nutze die Delivery Actions um den gesamten Kommunikationsfluss zu automatisieren. Du musst keine einzige E-Mail manuell versenden.
:::

## Kundenportal

Teilnehmer sehen ihre gebuchten Events im Kundenportal:

- **Event-Übersicht** - Alle gebuchten Events auf einen Blick
- **Ticket-Details** - Buchungsnummer, Teilnahme-Art, Status
- **Tagesplan** - Tagesansicht bei mehrtägigen Events
- **Stornierung** - Mit Bestätigungsdialog, Stornierungsbedingungen werden angezeigt
- **Join-Button** - Direkter Zugang zu Online-Events
- **Einladungs-Management** - Tickets an andere Personen weiterleiten

:::info[Hinweis]
Auch kostenlose Events können eine Anmeldung erfordern. So weißt du wer kommt und kannst automatische Erinnerungen versenden.
:::
