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

### Beispiel-Prompt für Morning-Check

```
Lies CLAUDE.md, scanne die context.md aller aktiven Projekte
unter projects/ und gib mir einen knappen Lagebericht plus drei
Prioritaeten fuer heute.

Beruecksichtige Deadlines aus den context-Dateien.
```

### Typische Antwort

```
Aktive Projekte (3):

- Nexus: 4 offene Bugs, davon 1 kritisch (Stripe-Webhook timeout).
  Provider-Deploy steht aus.
- SUYL: 2 offene Tasks, beide niedrige Prio. Kunde wartet aktuell
  nichts dringendes.
- Open Campus Kurs: morgen Termin 1, Vorbereitung steht auf 70 Prozent.

Drei Prioritaeten heute:

1. Nexus Stripe-Webhook fixen (kritisch, blockiert Kundenkaeufe)
2. Open Campus Termin 1 Konzept finalisieren (Deadline morgen 17:00)
3. Provider-Deploy nach Bugfix-Verifikation
```

Das ist ein produktiver Start. 5 Minuten Investment, Kopf ist sortiert.

## Während der Arbeit

- **Alles was länger als 5 Minuten Aufmerksamkeit braucht** landet in seiner Projekt-context.md
- **Alles was schnell raus muss** kommt in `inbox.md` (einsortieren später)
- **Entscheidungen** bekommen einen Eintrag in der `decisions.md` (Datum + Warum)
- **Meetings** landen in `meetings/YYYY-MM-DD-thema.md`

### Beispiel: ein Vormittag

09:00 - Morning-Check, Tagesfile angelegt, drei Prios festgelegt.
09:15 - Stripe-Webhook-Bug. In `projects/nexus/context.md` Bug-Beschreibung notieren, in Code reinspringen.
10:30 - Bug gefixt, Test geschrieben. context.md updaten ("Bug XYZ behoben, deployed auf dev"), Commit, Push.
10:45 - Mail vom Kunden mit neuer Anforderung. Notiz nach `projects/kunde-x/context.md` unter "Offene Themen" hinzu, sofort als unbearbeitet markieren.
11:00 - Idee für YouTube-Video während Kaffeekochen. Nicht jetzt verfolgen - rein in `inbox.md` mit zwei Sätzen.
11:15 - Open Campus Konzept weiter. Konkrete Änderungen direkt in `projects/opencampus-kurs/termin-01-konzept.md`.

Wichtig: Wiki-Pflege ist nicht "extra Arbeit" - es ist die Arbeit. Du dokumentierst was du sowieso machst.

## Claude Code als Tagesbegleiter

Muster die funktionieren:

### Briefing am Morgen

```
Lies meine context.md aller aktiven Projekte und gib mir einen Lagebericht.
Sortiere nach Dringlichkeit. Ich habe heute 6 Stunden Zeit.
```

### Problem-Besprechung

```
Das Projekt XYZ haengt an Thema ABC.
Was ist das Problem aus meiner context.md ersichtlich?
Liste mir drei moegliche Wege vor mit Pro und Contra.
```

### Schreibhilfe mit Kontext

```
Ich muss eine Mail an Kunde Z schreiben. Schau in
projects/kunde-z/context.md was wir besprochen haben und schreibe
einen Entwurf. Ton: freundlich, professionell, knapp.
```

### Zusammenfassung am Abend

```
Fasse die Aenderungen in daily/heute und in den Projekt-contexts
zum Tagesende zusammen. Was wurde erledigt, was steht noch offen.
```

### Recherche mit Memory

```
Wir hatten schon mal das Thema X. Suche im Wiki nach allen
Erwaehnungen und fasse zusammen was wir bisher dazu wissen.
```

## Der Freitag-Rückblick

Einmal pro Woche, 15 Minuten:

1. `daily/` der Woche durchschauen
2. Was ist passiert - in die jeweiligen project/context.md übertragen
3. Erledigte Todos abhaken
4. Neue Erkenntnisse in `reference/` ablegen falls wiederverwendbar
5. `inbox.md` leerziehen

Claude Code hilft:

```
Lies alle daily-Dateien dieser Woche (daily/2026-04-XX.md) und
ziehe Erkenntnisse pro Projekt raus. Schlage mir vor was in welche
context.md uebertragen werden sollte.
```

## Was NICHT passieren darf

### Anti-Muster 1: inbox.md wird Datenfriedhof

inbox.md sammelt 200 ungeordnete Notizen, du schaust nie rein, der Wert ist null.

**Lösung:** wöchentlich aufräumen ist Pflicht. Wenn du es nicht schaffst, ist inbox.md nicht das richtige Tool für dich - dann lieber sofort in die richtige Datei.

### Anti-Muster 2: daily-Dateien werden Romane

Du schreibst täglich eine Seite Tagebuch, das frisst Zeit, niemand liest es.

**Lösung:** 5 bis 10 Stichpunkte reichen. Was lief, was steht an, was war neu. Maximal 10 Minuten pro Tag.

### Anti-Muster 3: Du pflegst aber nutzt nicht

Du legst brav alle Dateien an, fragst Claude aber nie was. Wiki ist dann nur Buchhaltung.

**Lösung:** mindestens einmal pro Tag eine echte Frage an Claude mit Wiki-Kontext. Sonst sparst du dir das Pflegen.

### Anti-Muster 4: Perfektionismus

Du willst die "perfekte" Struktur, das "perfekte" Template. Nichts wird je live.

**Lösung:** schlechtes laufendes System schlägt perfektes ungebautes System. Anfangen, anpassen.

## Commit-Rhythmus

- **Nach jeder Session:** add + commit + push. Als "Backup".
- **Commit-Nachricht darf kurz sein:** "Tagesabschluss", "Meeting XYZ", "Projekt YZA Update".
- **Wenn du GitHub Desktop nutzt:** daran gewöhnen, das Fenster offen zu lassen. Die grüne Punktzahl erinnert dich.

## Mobile Nutzung

Wenn du unterwegs bist und eine Idee hast:

- **Schnellste Option:** GitHub Web-UI - inbox.md direkt im Browser editieren und commiten
- **Mit App:** Obsidian Mobile mit Git-Plugin (Android, iOS) für vollständigen Lese- und Schreibzugriff
- **iOS spezifisch:** Working Copy App + 1Writer als Editor, beide kostenpflichtig aber gut
- **Simpelste Option:** Notiz im Handy, später manuell übertragen

Mein Tipp: nicht zu viel Energie in Mobile-Workflows stecken. Die meiste Arbeit am Wiki passiert eh am Rechner. Mobile reicht für Quick Capture in inbox.md.

## Der 30-Tage-Test

Wenn du das Second Brain 30 Tage durchziehst und danach nicht mehr missen willst: es funktioniert für dich.

Wenn du es nach 30 Tagen nicht nutzt: entweder die Struktur passt nicht (anpassen) oder der Alltag lässt es nicht zu (System vereinfachen).

:::tip[Minimum Viable Wiki]
Besser täglich 3 Zeilen als wöchentlich eine Seite. Routine schlägt Perfektion.
:::
