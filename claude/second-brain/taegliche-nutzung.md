---
title: Tägliche Nutzung
order: 6
excerpt: Wie dein Second Brain im Alltag läuft - Routinen die funktionieren
---

# Tägliche Nutzung

Ein Second Brain das du nicht nutzt ist wertlos. Ein Second Brain das du täglich pflegst ist unbezahlbar. Hier kommen Routinen die sich in der Praxis bewährt haben.

## Der 5-Minuten-Morning-Check

Jeden Arbeitstag, am Anfang:

1. `inbox.md` durchgehen - Ideen von gestern einsortieren
2. `daily/YYYY-MM-DD.md` anlegen (Datum als Dateiname)
3. Claude Code fragen: "Was sollte ich heute priorisieren?"
4. Die Antwort kurz prüfen, drei Top-Aufgaben ins Tagesfile

TODO: Beispiel-Prompt und typische Antwort.

## Während der Arbeit

- **Alles was länger als 5 Minuten Aufmerksamkeit braucht** landet in seiner Projekt-context.md
- **Alles was schnell raus muss** kommt in `inbox.md` (einsortieren später)
- **Entscheidungen** bekommen einen Eintrag in der `decisions.md` (Datum + Warum)
- **Meetings** landen in `meetings/YYYY-MM-DD-thema.md`

TODO: Workflow-Beispiel eines durchschnittlichen Arbeitstages.

## Claude Code als Tagesbegleiter

Muster die funktionieren:

**Briefing am Morgen:**
> Lies meine context.md aller aktiven Projekte und gib mir einen Lagebericht.

**Problem-Besprechung:**
> Das Projekt XYZ hängt an Thema ABC. Liste mir drei mögliche Wege vor mit Pro und Contra.

**Zusammenfassung am Abend:**
> Fasse die Änderungen in daily/heute und in den Projekt-contexts zum Tagesende zusammen.

TODO: Mehr Muster mit realen Beispielen.

## Der Freitag-Rückblick

Einmal pro Woche, 15 Minuten:

1. `daily/` der Woche durchschauen
2. Was ist passiert - in die jeweiligen project/context.md übertragen
3. Erledigte Todos abhaken
4. Neue Erkenntnisse in `reference/` ablegen falls wiederverwendbar
5. `inbox.md` leerziehen

Claude Code hilft:
> Lies alle daily-Dateien dieser Woche und ziehe Erkenntnisse pro Projekt raus.

## Was NICHT passieren darf

- **inbox.md wird zum Datenfriedhof.** Wöchentlich aufräumen oder ganz weglassen.
- **daily-Dateien werden Ewigkeit-Romane.** Stichpunkte reichen. 10 Zeilen pro Tag sind ein guter Schnitt.
- **Du pflegst das Wiki, nutzt aber Claude nie damit.** Dann ist es nur Buchhaltung. Nutze es aktiv.

TODO: Anti-Muster mit Beispielen.

## Commit-Rhythmus

- **Nach jeder Session:** add + commit + push. Als "Backup".
- **Commit-Nachricht darf kurz sein:** "Tagesabschluss", "Meeting XYZ", "Projekt YZA Update".
- **Wenn du GitHub Desktop nutzt:** daran gewöhnen, das Fenster offen zu lassen. Die grüne Punktzahl erinnert dich.

## Mobile Nutzung

Wenn du unterwegs bist und eine Idee hast:

- **Schnellste Option:** GitHub Web-UI - `inbox.md` direkt im Browser editieren und commiten
- **Mit App:** Obsidian mit Git-Plugin, oder Working Copy App (iOS) + beliebiger Markdown-Editor
- **Simpelste Option:** Notiz im Handy, später manuell übertragen

TODO: Konkrete Apps mit Setup.

## Der 30-Tage-Test

Wenn du das Second Brain 30 Tage durchziehst und danach nicht mehr missen willst: es funktioniert für dich.

Wenn du es nach 30 Tagen nicht nutzt: entweder die Struktur passt nicht (anpassen) oder der Alltag lässt es nicht zu (System vereinfachen).

:::tip[Minimum Viable Wiki]
Besser täglich 3 Zeilen als wöchentlich eine Seite. Routine schlägt Perfektion.
:::
