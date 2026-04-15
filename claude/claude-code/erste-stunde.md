---
title: Die erste Stunde mit Claude Code
order: 3
excerpt: Ein konkreter Pfad von App-Start zu erstem echten Ergebnis - 60 Minuten
---

# Die erste Stunde mit Claude Code

Nicht Theorie lesen - selber bauen. Hier ist der Pfad.

## Voraussetzungen

- Du hast die Claude App installiert (siehe [[installation|Installation]])
- Du bist eingeloggt
- Du hast einen Ordner mit dem du arbeiten willst (kann ein leerer Ordner sein, oder ein bestehendes Wiki/Projekt)

## Minute 0-15: Setup verifizieren

1. Claude App öffnen
2. Workspace verbinden: Ordner auswählen
3. Im Chat fragen: "Was siehst du in diesem Ordner?"
4. Antwort lesen - Claude listet die Dateien auf

Wenn das funktioniert, ist alles richtig eingerichtet. Falls Claude sagt "Ich sehe keine Dateien", den Workspace nochmal verbinden.

## Minute 15-30: Erste echte Aufgabe

Wähle etwas echtes aber kleines. Beispiele:

### Beispiel A: Wochenplan aufbauen

In der App fragen:

> Bau mir eine Markdown-Datei "wochenplan.md" mit einem Plan fuer diese Woche. Hier sind meine Termine und Ziele:
>
> - Montag: Kundenmeeting Max um 10 Uhr
> - Dienstag: Konzept fuer Projekt XYZ schreiben
> - Mittwoch: Workshop vorbereiten
>
> Ziele der Woche: Konzept fertig, zwei Akquise-Mails verschickt.

Claude legt die Datei an, du siehst sie im Ordner und kannst sie öffnen.

### Beispiel B: Notizen zusammenfassen

Lege manuell eine Datei `notes.md` an mit ein paar Stichpunkten zu einem Thema.

In der App fragen:

> Lies meine notes.md und fasse sie in 5 klaren Stichpunkten zusammen.
> Speichere die Zusammenfassung in summary.md.

Claude liest, fasst zusammen, legt die neue Datei an.

### Beispiel C: Dokument umstrukturieren

Hast du eine alte Notiz oder Doku die unübersichtlich ist?

> Lies die Datei XYZ.md und schlage eine bessere Struktur vor.
> Wenn ich zustimme, schreib die Datei neu.

Claude schlägt vor, du gibst OK, fertig.

## Minute 30-45: Iterieren

Die erste Antwort ist selten final. Üb dich in kurzen Folgeanweisungen:

- "Mach das kürzer."
- "Fehler: es passiert X statt Y."
- "Füge zusätzlich Z hinzu."
- "Anderer Ton: weniger formell."
- "Nutze die Stilregeln aus meiner CLAUDE.md."

Iteration ist normal. Das ist kein Zeichen dass etwas nicht funktioniert - das ist der Prozess.

### Was wenn die Antwort komplett daneben ist

Drei Möglichkeiten:

1. **Kontext fehlt:** "Ich hatte vergessen zu erwähnen: das Dokument ist für interne Stakeholder, nicht für Kunden. Bitte anpassen."
2. **Beispiel geben:** "So sollte es etwa aussehen: [Beispiel]. Versuch nochmal in dem Stil."
3. **Neu starten:** Wenn der Chat zu durcheinander ist, neuen Chat öffnen und mit klarerem Prompt starten.

## Minute 45-60: CLAUDE.md anlegen

Dies ist der wichtigste Schritt der ersten Stunde.

In der App:

> Lege im aktuellen Ordner eine Datei "CLAUDE.md" an mit folgendem Inhalt:
>
> # Wer ich bin
>
> [dein Name], [deine Rolle]. Ich arbeite an [Hauptthema].
>
> # Was dieser Ordner ist
>
> [eine Zeile - was ist hier drin]
>
> # Sprache und Stil
>
> - Deutsch, technische Begriffe Englisch
> - Echte Umlaute (ä, ö, ü, ß), nie ae/oe/ue
> - Du-Form, kein "Sie"
>
> # Regeln
>
> - Erledigte Aufgaben als [x] markieren
> - Keine API Keys oder Kundendaten in Dateien

Claude legt die Datei an. Ab jetzt liest Claude die CLAUDE.md bei jeder Frage in diesem Ordner. Antworten werden sofort spezifischer.

Stelle danach eine neue Frage in einem neuen Chat und sieh den Unterschied:

> Was sollte ich heute priorisieren?

Mit CLAUDE.md weiß Claude wer du bist und was du machst. Die Antwort ist konkret statt generisch.

## Was du in dieser ersten Stunde gelernt hast

1. Claude kann Dateien in deinem Ordner lesen und schreiben
2. Iteration ist normal und produktiv
3. CLAUDE.md macht Antworten dramatisch besser
4. Du brauchst kein Coding-Wissen für nichts davon

## Was als nächstes

- [[mental-model|Mental Model]] - warum Claude Code "alles oder nichts" ist
- [[wiki-und-claude-md|Wiki und CLAUDE.md]] - die wichtigste Angewohnheit aufbauen
- [[../second-brain/setup|Second Brain aufbauen]] - dein erstes echtes Wiki

:::tip[Hausaufgabe für die nächste Woche]
Nutze Claude Code jeden Tag mindestens einmal mit einer echten Aufgabe. Nicht spielen - echte Arbeit. Nach 7 Tagen merkst du was es kann und was nicht.
:::
