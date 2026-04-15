---
title: Workflow-Beispiele
order: 9
excerpt: Echte Workflows - nicht Hello World, sondern wie man es wirklich nutzt
---

# Workflow-Beispiele

Keine abstrakten Beispiele. Echte Workflows die in der Praxis täglich laufen, alle in der Claude App, ohne Terminal.

## Workflow 1: Morgen-Routine

**Was passiert:** Claude liest dein Wiki, schaut in deinen Kalender, schlägt Prioritäten vor.

**Setup:** Wiki als Workspace verbunden, Kalender-Connector aktiv.

**Ablauf:**

1. App öffnen, Wiki-Workspace aktiv
2. Frage: "Was steht heute an? Schau ins Wiki und in meinen Kalender."
3. Claude liest CLAUDE.md, scannt aktive Projekte, holt Termine
4. Antwort: konkrete drei Prioritäten, geblockte Zeiten markiert
5. "Übernimm das in mein heutiges Tagesfile."
6. Claude legt die Datei an oder ergänzt sie

**Zeitaufwand:** 5 Minuten. Sortierter Kopf für den ganzen Tag.

## Workflow 2: Bugfix mit Kontext

**Was passiert:** Du beschreibst einen Bug, Claude liest die relevanten Dateien, schlägt Fix vor, du genehmigst.

**Setup:** Projekt als Workspace verbunden.

**Ablauf:**

1. Frage: "Im Projekt XYZ wirft die Funktion handlePayment einen Fehler bei ungültigen Karten. Schau dir die Datei an und schlage einen Fix vor."
2. Claude öffnet handlePayment, analysiert
3. Claude zeigt vorgeschlagene Änderung
4. Du klickst "Übernehmen" oder "Anpassen"
5. Optional: "Schreib einen kurzen Test dazu."
6. Claude legt die Test-Datei an

**Wichtig:** auch ohne Code-Wissen funktioniert das. Du beschreibst das Problem in Worten, Claude macht den Code-Teil.

## Workflow 3: Wochen-Zusammenfassung für Kunden

**Was passiert:** Claude nimmt deine Tagesnotizen und Projekt-Updates und schreibt einen Status-Bericht.

**Setup:** Wiki als Workspace, Kunde hat eigenen Projekt-Ordner.

**Ablauf:**

1. Frage: "Schau in projects/kunde-x/ und in die daily-Dateien dieser Woche. Was haben wir für Kunde X erledigt?"
2. Claude listet die Aktivitäten auf
3. "Schreib daraus einen Status-Bericht für die Kunden-Mail. Tonalität: freundlich-professionell, kurz."
4. Claude schreibt den Entwurf
5. Du editierst, kopierst, sendest die Mail

**Zeitaufwand:** 10 Minuten statt 45 Minuten manuelles Zusammensuchen.

## Workflow 4: Landingpage aus Briefing

**Was passiert:** Du beschreibst was du brauchst, Claude baut die HTML-Seite.

**Setup:** Projekt-Ordner als Workspace, optional Beispiel-Dateien für Stil.

**Ablauf:**

1. Frage: "Bau mir eine Landingpage für das Produkt YZA. Hier ist das Briefing: [Briefing]. Stil wie in beispiele/landingpage-x.html. Speichere als yza/index.html."
2. Claude liest das Beispiel, baut die Seite
3. Du schaust dir die Datei im Browser an
4. Iteration: "Header zu groß", "Sektion XYZ raus", "Farben anders"
5. Claude passt an, du prüfst

**Wichtig:** auch ohne HTML-Wissen funktioniert das. Du beschreibst was du sehen willst, Claude baut.

## Workflow 5: Customer Support aufräumen

**Was passiert:** Support-Mails zusammenfassen, Pattern erkennen, wiederkehrende Themen identifizieren.

**Setup:** Workspace mit Support-Notizen oder Connector zu deinem Support-Tool.

**Ablauf:**

1. Frage: "Schau dir die Support-Tickets der letzten zwei Wochen an. Welche Themen kommen mehrfach? Was sollten wir in die Doku aufnehmen?"
2. Claude analysiert, gruppiert
3. Antwort: "Drei Themen tauchen wiederholt auf: Onboarding-Schritt 4, Login-Probleme nach Update, fehlende Anleitung für Feature X."
4. "Schreib zu Thema 1 einen Doku-Eintrag."
5. Claude schreibt den Entwurf, du veröffentlichst

## Workflow 6: Meeting-Vorbereitung

**Was passiert:** Vor einem wichtigen Meeting weiß Claude was relevant ist.

**Setup:** Wiki mit Projekt-Kontext und Meeting-Historie.

**Ablauf:**

1. Frage: "Ich habe in 30 Minuten Meeting mit Kunde X. Was ist der aktuelle Stand, was sind offene Themen, was waren die letzten Entscheidungen?"
2. Claude liest projects/kunde-x/context.md, decisions.md, letzte meetings/-Notizen
3. Antwort: Kompaktes Briefing mit Status, offenen Themen, Vorbereitungspunkten
4. "Schreib mir eine Meeting-Notiz-Vorlage für heute."
5. Claude legt die Datei an, fertig zum Mitschreiben

## Workflow 7: Newsletter aus Wissen

**Was passiert:** Wiki ist deine Wissensbasis, Newsletter entstehen daraus.

**Setup:** Wiki mit gepflegten reference/-Dateien, früheren Newslettern als Stil-Beispiel.

**Ablauf:**

1. Frage: "Was waren die spannendsten Erkenntnisse aus den letzten 2 Wochen? Schau in daily/ und reference/."
2. Claude listet Themen auf
3. Du wählst eines: "Mach daraus einen Newsletter-Entwurf. Stil wie in newsletter/2026-03-XX.md."
4. Claude schreibt
5. Du finalisierst, sendest

## Was allen Workflows gemeinsam ist

- **Kontext liegt im Wiki**, Claude muss nicht raten
- **Klarer Startpunkt und klares Ziel** im Prompt
- **Zwischenergebnisse werden geprüft**, nicht erst das Endergebnis
- **Wichtige Teile landen zurück im Wiki** (Decisions, Updates)
- **Iteration ist eingeplant**, nicht als Versagen

## Was du brauchst um diese Workflows zu fahren

- Claude App installiert
- Workspace verbunden
- CLAUDE.md gepflegt
- Wiki mit zumindest Basis-Struktur
- Bereitschaft zu iterieren

Mehr nicht. Insbesondere: **kein Coding-Wissen, keine Kommandozeile**.

:::tip[Eigene Workflows finden]
Schau dir an wo du jeden Tag manuell zwischen Apps wechselst und kopierst. Das ist ein Workflow-Kandidat. Wenn du nicht weißt wo anfangen: nimm Workflow 1 (Morgen-Routine) und mach das eine Woche täglich.
:::
