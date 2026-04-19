---
title: Kosten im Griff halten
order: 11
excerpt: Was Claude Code kostet und wie du Überraschungen vermeidest
---

# Kosten im Griff halten

Claude Code läuft über dein Anthropic-Abonnement. Die Kosten können wachsen wenn du es intensiv nutzt - wer weiß worauf zu achten ist, bleibt im Rahmen.

## Preismodelle

**Free**

- Begrenzte Nutzung pro Tag
- Reicht zum Reinschnuppern
- Kein dauerhaftes Arbeiten möglich

**Pro**

- Pauschale pro Monat
- Höhere Limits
- Reicht für Solo-Nutzer die Claude Code täglich verwenden
- Empfohlener Einstieg

**Max**

- Höhere Pauschale, größere Limits
- Sinnvoll wenn du täglich mehrere Stunden mit Claude arbeitest
- Auch wenn du große Workspaces hast die viele Tokens pro Frage verbrauchen

**API (für Entwickler)**

- Pay per Token
- Nur relevant wenn du eigene Apps mit Claude baust, nicht für die App-Nutzung

Aktuelle Preise und Limits siehst du auf claude.ai/upgrade.

## Wo Tokens fressen werden

In der Claude App bezahlst du mit deinem Abo, technisch werden aber Tokens verbraucht. Je mehr Tokens, desto schneller erreichst du Limits.

Token-Fresser:

- **Lange CLAUDE.md** die bei jedem Start geladen wird (auch wenn du sie nicht direkt fragst)
- **Workspaces mit vielen großen Dateien** (Claude scannt was relevant ist)
- **Lange Chat-Verläufe** ohne Reset
- **Wiederholtes Lesen großer Dateien** ("Lies nochmal alles" mehrmals hintereinander)
- **Komplette Workflows mit vielen Zwischenschritten** in einem einzigen Chat

## Kosten reduzieren

**1. CLAUDE.md schlank halten**

Eine 200-Zeilen-CLAUDE.md wird bei jeder Frage mitgeladen. 50 Zeilen reichen meistens. Spezifische Details in dedizierte Dateien auslagern, die nur bei Bedarf gelesen werden.

**2. Aufgaben in kleinere Schritte zerlegen**

Statt einem Mega-Chat mit 20 Iterationen: lieber neue Chats für neue Themen. Spart Tokens, hält Kontext sauber.

**3. Nur den nötigen Workspace verbinden**

Wenn du an Projekt A arbeitest, brauchst du Projekt B nicht offen. Weniger Workspace = weniger Tokens für Datei-Scanning.

**4. Konkret fragen**

Schlecht: "Schau dir alle Dateien im Wiki an und sag mir was wichtig ist."
Gut: "Schau in projects/kunde-x/context.md und sag mir die nächsten Schritte."

Konkrete Pfade sparen das große Scannen.

**5. Caches nutzen**

Wenn du im selben Chat mehrfach das Gleiche fragst, nutzt Claude internen Cache. Funktioniert automatisch, du musst nichts tun - aber Bewusstsein hilft: in einem Chat bleiben wenn du an einem Thema dranbist, statt jedes Mal neu starten.

## Monitoring

In der App siehst du normalerweise unter **Einstellungen → Usage** wie viel du verbraucht hast. Pro-Plan-Nutzer haben oft Tageslimits, Max-Nutzer höhere.

Wenn du Limits erreichst:
- Pro-Tag-Limit: am nächsten Tag wieder normal
- Pro-Stunden-Limit: ein paar Stunden warten
- Subscription-Limit: Plan upgraden oder warten bis nächste Abrechnungsperiode

## Welche Variante für wen

| Situation | Empfehlung |
|---|---|
| Erstes Reinschnuppern | Free |
| Solo-Nutzer, gelegentlich | Pro |
| Solo-Nutzer, täglich | Pro |
| Solo-Nutzer, mehrere Stunden täglich | Max |
| Team mit gemeinsamen Workspaces | Pro pro Person, oder Team-Plan wenn verfügbar |
| Du baust eigene Apps mit Claude | API zusätzlich |

:::tip[Faustregel]
Bei der Pro-Variante kommst du als Einzelnutzer meistens durch, auch bei intensiver Wiki-Pflege und mehreren Stunden pro Tag. Erst wenn du wirklich hauptberuflich mit Claude Code arbeitest und groß angelegte Aufgaben fährst, lohnt sich Max.
:::
