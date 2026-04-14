---
title: Kosten im Griff halten
order: 11
excerpt: Was Claude Code kostet und wie du Überraschungen vermeidest
---

# Kosten im Griff halten

Claude Code läuft über dein Anthropic-Abonnement oder über API-Kosten. Die Kosten können schnell wachsen - wer weiß worauf zu achten ist, bleibt im Rahmen.

## Preismodelle

- **Pro Abo** - Monatliche Pauschale, Limits pro Zeitfenster
- **Max Abo** - Mehr Limits, höhere Pauschale
- **API** - Pay per Token

TODO: Aktuelle Preise nachtragen und Vor-/Nachteile erklären.

## Wo Tokens fressen werden

- Lange CLAUDE.md die bei jedem Start geladen wird
- Wiki-Dateien die komplett gelesen werden statt nur das Relevante
- Wiederholte Read-Operationen auf große Dateien

TODO: Konkrete Beispiele mit Token-Zahlen.

## Kosten reduzieren

- Aufgaben in kleinere Schritte zerlegen (oft billiger als ein langer Chat)
- Modellwahl: Sonnet statt Opus wenn möglich
- Caches nutzen: wiederholte Anfragen können gecached werden
- Keine großen Logs oder generierten Dateien in Kontext laden

TODO: Konkrete Maßnahmen mit Einspareffekt.

## Monitoring

TODO: Wie man in Claude Code sieht wie viele Tokens man schon verbraucht hat, Dashboard im Anthropic Console.

:::tip[Faustregel]
Bei der Pro-Variante kommst du als Einzelnutzer meist durch. Erst wenn du täglich mehrere Stunden am Stück Claude Code nutzt, wird Max sinnvoll.
:::
