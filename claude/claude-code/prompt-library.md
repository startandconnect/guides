---
title: Prompt Library
order: 6
excerpt: Konkrete Prompts für typische Situationen - copy, paste, anpassen
---

# Prompt Library

Keine Theorie, nur Prompts die in der Claude App funktionieren. Jeder Prompt hat: **Wann benutzen**, **Was anpassen**, **Der Prompt**, **Typische Fallen**.

Voraussetzung: dein Wiki ist als Workspace verbunden, CLAUDE.md ist gepflegt.

## 1. Neues Wiki aufsetzen

**Wann benutzen:** Du willst ein persönliches Wiki anlegen, weißt aber nicht wo anfangen.

**Was anpassen:** Deine Rolle, deine Hauptthemen, dein Projekt-Schwerpunkt.

**Der Prompt:**

```
Lege im aktuellen Workspace die Grundstruktur fuer ein persoenliches
Wiki an. Ich bin [DEINE ROLLE], arbeite hauptsaechlich an [HAUPTTHEMEN].

Ich brauche:
- CLAUDE.md mit Wer-ich-bin und Sprache/Stil-Regeln
- README.md fuer Menschen
- inbox.md fuer Quick Capture
- Ordner projects/, reference/, daily/
- Beispieleintrag in projects/ als Vorlage

Frag mich nach Details die du brauchst, lege erst dann an.
```

**Typische Fallen:** wenn du keine Details auf Rückfragen gibst, baut Claude Generisches. Lieber konkret antworten.

## 2. Neues Projekt im Wiki anlegen

**Wann benutzen:** Du startest ein neues Projekt und willst eine saubere context.md.

**Was anpassen:** Projektname, Typ, kurze Beschreibung.

**Der Prompt:**

```
Lege ein neues Projekt an: projects/[PROJEKT-NAME]/context.md.

Typ: [Eigenes Produkt / Kundenprojekt / Lernprojekt]
Worum es geht: [eine bis zwei Saetze]

Nutze die Struktur die wir im Wiki etabliert haben (siehe andere
context.md als Referenz). Frag mich nach Status, Zielen und drei
ersten offenen Aufgaben.
```

## 3. Tagesstart

**Wann benutzen:** Morgens vor der Arbeit, um Prioritäten zu sortieren.

**Was anpassen:** Anzahl Stunden die du heute hast.

**Der Prompt:**

```
Lies CLAUDE.md, scanne die context.md aller aktiven Projekte unter
projects/ und gib mir einen Lagebericht plus drei Prioritaeten fuer
heute.

Beruecksichtige Deadlines und kritische Bugs. Ich habe heute [X]
Stunden Zeit. Wenn du eine Tagesnotiz fuer heute (daily/YYYY-MM-DD.md)
anlegen sollst, sag Bescheid was du reinschreiben willst.
```

## 4. Idee zu Scope schärfen

**Wann benutzen:** Du hast eine vage Projektidee und willst Klarheit.

**Was anpassen:** Die rohe Idee.

**Der Prompt:**

```
Ich habe eine Idee: [BESCHREIBUNG, gerne unklar].

Hilf mir das zu schaerfen. Stell mir Fragen zu:
- Zielgruppe (wer hat das Problem)
- Konkretes Problem (was nervt heute)
- Minimum Viable Version (was muss zu Tag 1 funktionieren)
- Erfolgskriterien (wann weiss ich dass es funktioniert)

Stell die Fragen einzeln, nicht alle auf einmal. Wenn wir durch sind,
fasse das Ergebnis als context.md fuer ein neues Projekt zusammen.
```

## 5. Fremde API verstehen

**Wann benutzen:** Du hast eine API-Doku vor dir und willst sie schnell verstehen.

**Was anpassen:** API-Name und Doku-URL.

**Der Prompt:**

```
Ich will mit der API von [SERVICE] arbeiten. Doku ist hier:
[URL oder lokaler Pfad].

Erklaere mir auf einer Seite: Auth-Methode, die wichtigsten 5 bis 10
Endpoints, typische Use Cases, was schief gehen kann.

Lege das Ergebnis als reference/[service]-api.md im Wiki ab.
```

## 6. Workflow dokumentieren

**Wann benutzen:** Du hast einen Workflow (in n8n, im Code, oder als manueller Prozess) und willst ihn dokumentieren.

**Was anpassen:** Pfad zum Workflow oder Beschreibung.

**Der Prompt:**

```
Schau dir [DATEI / LINK / BESCHREIBUNG] an und schreibe eine
verstaendliche Dokumentation:
- Was macht der Workflow
- Welche Inputs bekommt er
- Welche Outputs erzeugt er
- Was sind die Schritte intern
- Was kann schief gehen

Lege als reference/[name]-workflow.md ab. Sprache: einfach, fuer
mein zukuenftiges Ich in 6 Monaten.
```

## 7. Code Review light

**Wann benutzen:** Du hast etwas selbst geschrieben und willst einen Check.

**Was anpassen:** Pfad zur Datei.

**Der Prompt:**

```
Schau dir [DATEI] an und gib mir Feedback.

Fokus:
- Klarheit (versteht das jemand der den Kontext nicht hat)
- Logik (gibt es offensichtliche Fehler)
- Sicherheit (sind irgendwo Geheimnisse hardcoded)

Keine Stil-Diskussionen, keine Mikro-Optimierungen. Wenn alles ok
ist: sag das einfach.
```

## 8. Meeting-Notes strukturieren

**Wann benutzen:** Rohnotizen aus einem Meeting sollen zu sauberer Doku werden.

**Was anpassen:** Pfad zu den Rohnotizen, Datum, Thema.

**Der Prompt:**

```
Hier sind meine Rohnotizen aus dem Meeting heute:
[NOTIZEN ODER PFAD ZUR DATEI]

Mache daraus eine strukturierte Meeting-Notiz mit:
- Teilnehmer
- Themen die besprochen wurden
- Entscheidungen
- Action Items mit Zustaendigkeit

Lege als meetings/YYYY-MM-DD-[thema].md ab.
```

## 9. Wochenrückblick

**Wann benutzen:** Freitag nachmittags, Rückblick auf die Woche.

**Was anpassen:** nichts, funktioniert generisch.

**Der Prompt:**

```
Lies alle daily-Dateien dieser Woche (Montag bis heute) und ziehe
Erkenntnisse pro Projekt.

Fuer jedes betroffene Projekt:
- Was wurde erledigt
- Welche neuen Themen sind aufgetaucht
- Welche Entscheidungen wurden getroffen

Schlage mir vor was in welche project/context.md uebertragen werden
sollte. Erst nach meiner Zustimmung anpassen.
```

## 10. Debugging-Partner

**Wann benutzen:** Fehler oder Problem, du kommst nicht weiter.

**Was anpassen:** Beschreibung des Problems.

**Der Prompt:**

```
Ich habe folgendes Problem: [BESCHREIBUNG].

Was ich schon probiert habe:
- [ANSATZ 1]
- [ANSATZ 2]

Schau in [RELEVANTE DATEIEN]. Was uebersehe ich? Liste 3 wahrscheinliche
Ursachen mit Pruefschritten.
```

## 11. Prompt-Verbesserer

**Wann benutzen:** Dein Prompt liefert schlechte Ergebnisse, du weißt nicht warum.

**Was anpassen:** Dein Original-Prompt und das schlechte Ergebnis.

**Der Prompt:**

```
Mein Prompt war: [ORIGINAL-PROMPT]
Das Ergebnis war: [SCHLECHTES ERGEBNIS]
Was ich eigentlich wollte: [ZIEL]

Was sollte ich am Prompt aendern damit ich mein Ziel erreiche?
Schlage mir eine bessere Version vor.
```

## 12. Abschluss-Reflexion

**Wann benutzen:** Projekt oder Phase abgeschlossen, Learnings sichern.

**Was anpassen:** Projektname.

**Der Prompt:**

```
Das Projekt [NAME] ist abgeschlossen. Schau dir context.md, decisions.md
und alle daily-Dateien an die das Projekt erwaehnen.

Schreibe eine Abschluss-Reflexion:
- Was lief gut
- Was war schwierig
- Was wuerde ich beim naechsten Mal anders machen
- Welche Erkenntnisse sind generell uebertragbar (in reference/ ablegen)

Lege als projects/[NAME]/abschluss.md ab.
```

:::tip[Beitragen]
Die besten Prompts entstehen aus echten Alltagsfragen. Wenn ein Prompt dir hilft und hier noch nicht steht: schick uns das Feedback, wir nehmen es auf.
:::
