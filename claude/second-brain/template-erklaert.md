---
title: Das Template erklärt
order: 7
excerpt: Was steckt im sac-brain-template, warum so und wie du es an dich anpasst
---

# Das Template erklärt

Das Template unter `github.com/startandconnect/sac-brain-template` ist kein starrer Rahmen, sondern ein durchdachter Startpunkt. Hier erfährst du was drin ist und warum.

TODO: URL prüfen sobald Template-Repo existiert.

## Was du bekommst

Nach dem Clone hast du folgende Struktur:

```
sac-brain-template/
├── CLAUDE.md                ← vorausgefüllt, du passt an
├── README.md                ← für Menschen
├── inbox.md                 ← leer, zum Quick Capture
├── daily/
│   └── _template.md         ← Vorlage für Tagesnotizen
├── projects/
│   └── beispiel-projekt/
│       └── context.md       ← als Referenz wie context.md aussieht
├── reference/
│   ├── _template.md         ← Vorlage für Referenzseiten
│   └── example-api.md       ← Beispiel einer API-Referenz
├── meetings/
│   └── _template.md         ← Vorlage für Meeting-Notes
└── .gitignore               ← vorbereitet für sensible Dateien
```

TODO: Baum aktualisieren sobald Template final ist.

## Warum diese Dateien

### CLAUDE.md
Muss da sein, sonst hat Claude keinen Kontext. Vorausgefüllt als Template mit Platzhaltern - du ersetzt sie durch deine echten Informationen. Details: [[claude-md-anleitung|CLAUDE.md richtig schreiben]].

### README.md
Für Menschen die dein Repo sehen. Auch für dich in 6 Monaten. Erklärt wofür das Repo ist und wie man es nutzt.

### inbox.md
Leer, für schnelle Ideen. Eine einzige Datei statt vielen kleinen. Wöchentlich einsortieren.

### daily/ mit _template.md
Pro Tag eine Datei. Template gibt die Struktur vor: was lief, was steht an, was habe ich gelernt.

### projects/beispiel-projekt/
Zeigt wie ein Projekt aussieht. Lösche es wenn du magst - oder benutze es als Kopiervorlage.

### reference/
Für Dinge die du nachschlägst. APIs, Prozesse, Listen. Nicht Tagesaktuelles.

### meetings/
Meeting-Notizen mit Template. Schema: Datum, Teilnehmer, Themen, Entscheidungen, offene Punkte.

### .gitignore
Verhindert dass du versehentlich sensible Dateien commitest. `.env`, `secrets.md`, `*.key` sind ausgeschlossen.

## Wie du es anpasst

Das Template ist kein Gesetz. Typische Anpassungen:

1. **CLAUDE.md personalisieren.** Pflicht. Machst du in den ersten 15 Minuten.
2. **Beispiel-Projekt löschen** wenn du keinen Platzhalter willst.
3. **Ordner umbenennen.** `projects/` heißen für manche lieber `kunden/` oder `baustellen/`.
4. **Eigene Ordner hinzufügen.** Brauchst du einen `content/` Ordner für Blog/YouTube? Rein damit.
5. **Ordner löschen die du nicht nutzt.** Wenn du keine Meetings hast, weg mit `meetings/`.

TODO: Konkrete Vorher/Nachher-Beispiele.

## Was du nicht ändern solltest

- **Die Idee einer CLAUDE.md.** Wenn du die streichst, fehlt Claude der Kontext.
- **Markdown als Format.** Alles andere funktioniert schlechter mit Claude Code.
- **context.md pro Projekt.** Einheitliche Einstiegsdatei ist Gold wert.

## Template-Updates pullen

Wenn wir das Template updaten (neue Best Practices, neue Beispiele), kannst du die Änderungen zu dir ziehen.

```bash
git remote add template https://github.com/startandconnect/sac-brain-template.git
git fetch template
git merge template/main --allow-unrelated-histories
```

TODO: Schritt-für-Schritt inklusive Merge-Konflikt-Handling falls nötig.

In GitHub Desktop geht es auch, braucht aber etwas Klickarbeit.

## Weiter

Wenn dein Template angepasst ist und das Grundgerüst steht:

- [[claude-md-anleitung|CLAUDE.md richtig schreiben]] - aus dem Platzhalter etwas Brauchbares machen
- [[taegliche-nutzung|Tägliche Nutzung]] - Routinen einführen
- [[advanced|Advanced]] - wenn die Basis läuft
