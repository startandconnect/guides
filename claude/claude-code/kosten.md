---
title: Kosten im Griff halten
order: 11
excerpt: Was Claude Code kostet und wie du Ueberraschungen vermeidest
---

# Kosten im Griff halten

Claude Code laeuft ueber dein Anthropic-Abonnement oder ueber API-Kosten. Die Kosten koennen schnell wachsen - wer weiss worauf zu achten ist, bleibt im Rahmen.

## Preismodelle

- **Pro Abo** - Monatliche Pauschale, Limits pro Zeitfenster
- **Max Abo** - Mehr Limits, hoehere Pauschale
- **API** - Pay per Token

TODO: Aktuelle Preise nachtragen und Vor-/Nachteile erklaeren.

## Wo Tokens fressen werden

- Lange CLAUDE.md die bei jedem Start geladen wird
- Wiki-Dateien die komplett gelesen werden statt nur das Relevante
- Wiederholte Read-Operationen auf grosse Dateien

TODO: Konkrete Beispiele mit Token-Zahlen.

## Kosten reduzieren

- Aufgaben in kleinere Schritte zerlegen (oft billiger als ein langer Chat)
- Modellwahl: Sonnet statt Opus wenn moeglich
- Caches nutzen: wiederholte Anfragen koennen gecached werden
- Keine grossen Logs oder generierten Dateien in Kontext laden

TODO: Konkrete Massnahmen mit Einspareffekt.

## Monitoring

TODO: Wie man in Claude Code sieht wie viele Tokens man schon verbraucht hat, Dashboard im Anthropic Console.

:::tip[Faustregel]
Bei der Pro-Variante kommst du als Einzelnutzer meist durch. Erst wenn du taeglich mehrere Stunden am Stueck Claude Code nutzt, wird Max sinnvoll.
:::
