---
title: Tägliche Nutzung
order: 6
excerpt: Wie dein Second Brain im Alltag läuft - Routinen die funktionieren
---

# Tägliche Nutzung

Ein Second Brain das du nicht nutzt ist wertlos. Ein Second Brain das du täglich pflegst ist unbezahlbar. Hier kommen Routinen die sich in der Praxis bewährt haben - alle in der Claude App.

## Der 5-Minuten-Morning-Check

Jeden Arbeitstag, am Anfang:

1. Claude App öffnen, Wiki-Workspace aktiv
2. `inbox.md` durchgehen oder Claude fragen "Was steht in meiner Inbox, schlage Einsortierung vor"
3. Tagesfile anlegen lassen: "Lege daily/[heutiges Datum].md an mit der Vorlage"
4. Claude fragen: "Was sollte ich heute priorisieren?"
5. Drei Top-Aufgaben in das Tagesfile übernehmen lassen

### Beispiel-Prompt für Morning-Check

```
Lies CLAUDE.md, scanne die context.md aller aktiven Projekte unter
projects/ und gib mir einen knappen Lagebericht plus drei
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

Soll ich diese drei Punkte in die heutige Tagesnotiz uebernehmen?
```

Das ist ein produktiver Start. 5 Minuten Investment, Kopf ist sortiert.

## Während der Arbeit

- **Alles was länger als 5 Minuten Aufmerksamkeit braucht** landet in seiner Projekt-context.md
- **Alles was schnell raus muss** kommt in `inbox.md` (einsortieren später)
- **Entscheidungen** bekommen einen Eintrag in der `decisions.md` (Datum + Warum)
- **Meetings** landen in `meetings/[Datum]-[thema].md`

Du musst die Dateien nicht selbst öffnen oder bearbeiten. Sag Claude was passieren soll:

> Trag in projects/nexus/context.md unter Offene Themen ein: Webhook timeout debuggen, Priority hoch.

> Schreib einen kurzen Eintrag in decisions.md von heute: Wir nehmen Stripe statt Lemon Squeezy. Begruendung: bessere DACH-Abdeckung.

> Lege meetings/[heutiges Datum]-kunde-x.md an, Vorlage anwenden.

### Beispiel: ein Vormittag

09:00 - Morning-Check, Tagesfile angelegt, drei Prios festgelegt.
09:15 - Stripe-Webhook-Bug. Claude fragen: "Trage in projects/nexus/context.md den Bug ein und schau dir webhook-handler.ts an."
10:30 - Bug gefixt. Claude fragen: "Aktualisiere context.md - Bug behoben, deployed auf dev."
10:45 - Mail vom Kunden mit neuer Anforderung. Claude: "Trag das in projects/kunde-x/context.md unter Offene Themen ein."
11:00 - Idee für YouTube-Video während Kaffeekochen. Selbst kurz in `inbox.md` notieren oder per App: "Notiere in inbox.md: Idee für Video XYZ - Aufhänger ist..."
11:15 - Open Campus Konzept weiter. Direkt in der App das Dokument bearbeiten lassen.

Wichtig: Wiki-Pflege ist nicht "extra Arbeit" - es ist die Arbeit. Du dokumentierst während du arbeitest.

## Claude als Tagesbegleiter

Muster die funktionieren:

### Briefing am Morgen

```
Lies meine context.md aller aktiven Projekte und gib mir einen
Lagebericht. Sortiere nach Dringlichkeit. Ich habe heute 6 Stunden Zeit.
```

### Problem-Besprechung

```
Das Projekt XYZ haengt an Thema ABC. Was ist das Problem aus meiner
context.md ersichtlich? Liste mir drei moegliche Wege vor mit Pro
und Contra.
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

Einmal pro Woche, 15 Minuten in der Claude App:

```
Lies alle daily-Dateien dieser Woche und ziehe Erkenntnisse pro
Projekt raus. Schlage mir vor was in welche context.md uebertragen
werden sollte. Frage mich vor jeder Aenderung.
```

Claude geht durch, du bestätigst, alles wird sauber konsolidiert.

Anschließend:

```
Pruefe inbox.md und schlage Einsortierung der noch offenen Punkte vor.
Wenn etwas zu alt ist (mehr als 4 Wochen) und nicht erledigt: vorschlagen
zu loeschen.
```

Inbox bleibt gepflegt, Wiki bleibt aktuell.

## Sichern (Push) - täglich oder nach Sessions

Damit nichts verloren geht und du auf anderen Geräten weitermachen kannst:

1. GitHub Desktop öffnen
2. Geänderte Dateien anschauen
3. Summary eintippen ("Tagesabschluss")
4. **Commit to main** klicken
5. **Push origin** klicken

Dauert 30 Sekunden. Mach das mindestens einmal pro Tag, besser nach jeder größeren Session.

## Was NICHT passieren darf

### Anti-Muster 1: inbox.md wird Datenfriedhof

inbox.md sammelt 200 ungeordnete Notizen, du schaust nie rein, der Wert ist null.

**Lösung:** wöchentlich aufräumen ist Pflicht. Wenn du es nicht schaffst, ist inbox.md nicht das richtige Tool für dich - dann lieber sofort in die richtige Datei (über Claude).

### Anti-Muster 2: daily-Dateien werden Romane

Du schreibst täglich eine Seite Tagebuch, das frisst Zeit, niemand liest es.

**Lösung:** 5 bis 10 Stichpunkte reichen. Was lief, was steht an, was war neu. Maximal 10 Minuten pro Tag.

### Anti-Muster 3: Du pflegst aber nutzt nicht

Du legst brav alle Dateien an, fragst Claude aber nie was. Wiki ist dann nur Buchhaltung.

**Lösung:** mindestens einmal pro Tag eine echte Frage an Claude mit Wiki-Kontext. Sonst sparst du dir das Pflegen.

### Anti-Muster 4: Perfektionismus

Du willst die "perfekte" Struktur, das "perfekte" Template. Nichts wird je live.

**Lösung:** schlechtes laufendes System schlägt perfektes ungebautes System. Anfangen, anpassen.

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
