---
title: Das Template erklärt
order: 7
excerpt: Was steckt im sac-brain-template, warum so und wie du es an dich anpasst
---

# Das Template erklärt

Das Template unter `github.com/startandconnect/sac-brain-template` ist kein starrer Rahmen, sondern ein durchdachter Startpunkt. Hier erfährst du was drin ist und warum.

## Was du bekommst

Nach dem Clone hast du folgende Struktur:

```
sac-brain-template/
├── CLAUDE.md                ← vorausgefuellt mit Platzhaltern, du passt an
├── README.md                ← fuer Menschen
├── inbox.md                 ← leer, zum Quick Capture
├── daily/
│   ├── _template.md         ← Vorlage fuer Tagesnotizen
│   └── README.md            ← erklaert das Daily-System
├── projects/
│   ├── _template/           ← Kopiervorlage fuer neue Projekte
│   │   └── context.md
│   └── beispiel-projekt/    ← Referenz wie context.md aussieht
│       └── context.md
├── reference/
│   ├── _template.md         ← Vorlage fuer Referenzseiten
│   └── example-api.md       ← Beispiel einer API-Referenz
├── meetings/
│   ├── _template.md         ← Vorlage fuer Meeting-Notes
│   └── README.md            ← Wann und wie Meetings dokumentieren
├── decisions.md             ← Firmenweite/wikiweite Entscheidungen
├── CHANGELOG.md             ← was hat sich im Wiki geaendert
└── .gitignore               ← vorbereitet fuer sensible Dateien
```

## Warum diese Dateien

### CLAUDE.md

Muss da sein, sonst hat Claude keinen Kontext. Vorausgefüllt als Template mit Platzhaltern - du ersetzt sie durch deine echten Informationen. Details: [[claude-md-anleitung|CLAUDE.md richtig schreiben]].

### README.md

Für Menschen die dein Repo sehen. Auch für dich in 6 Monaten wenn du dich fragst "wofür war das nochmal". Erklärt:

- Wofür ist dieses Wiki
- Wie ist es strukturiert
- Wie pflegt man es
- Wo fängt man an wenn man sich verloren fühlt

### inbox.md

Leer, für schnelle Ideen. Eine einzige Datei statt vielen kleinen. Wöchentlich einsortieren. Format: stichpunktartig, Datum optional.

### daily/_template.md und daily/README.md

Pro Tag eine Datei. Template gibt die Struktur vor: was lief, was steht an, was habe ich gelernt. README erklärt das System.

```markdown
# 2026-04-15

## Heute

- [ ] Aufgabe 1
- [ ] Aufgabe 2

## Erledigt

## Notizen

## Gelernt
```

### projects/_template/

Eine Vorlage zum Kopieren wenn du ein neues Projekt anlegst. Inklusive vorgefertigter context.md mit allen Standardabschnitten.

### projects/beispiel-projekt/

Zeigt wie ein gepflegtes Projekt aussieht. Lösche es wenn du magst - oder benutze es als Referenz.

### reference/

Für Dinge die du nachschlägst. APIs, Prozesse, Listen. Nicht Tagesaktuelles.

Eine `example-api.md` zeigt wie eine API-Referenz aussehen kann (Auth, Base URL, Endpoints, Beispiele).

### meetings/

Meeting-Notizen mit Template. Schema: Datum, Teilnehmer, Themen, Entscheidungen, offene Punkte. README erklärt wann ein Meeting wirklich dokumentiert werden sollte (Spoiler: nicht jedes).

### decisions.md

Wichtige Entscheidungen die wikiweit gelten. Format:

```markdown
## YYYY-MM-DD - Titel der Entscheidung
**Was:** kurz
**Warum:** Begruendung
**Alternativen die verworfen wurden:** kurz
```

### CHANGELOG.md

Was sich im Wiki strukturell geändert hat. Hilft beim Onboarding und wenn du dich nach Monaten fragst "wann habe ich diese Konvention eingeführt".

### .gitignore

Verhindert dass du versehentlich sensible Dateien commitest. Standardmäßig ausgeschlossen:

```
.env
.env.*
*.key
*.pem
secrets.md
private/
```

Wenn du eine Datei mit Geheimnissen brauchst, lege sie unter `private/` ab und sie wird automatisch ignoriert.

## Wie du es anpasst

Das Template ist kein Gesetz. Typische Anpassungen:

### 1. CLAUDE.md personalisieren (Pflicht)

Machst du in den ersten 15 Minuten. Platzhalter raus, deine echten Informationen rein.

### 2. Beispiel-Projekt löschen

Wenn du keinen Platzhalter willst, sag in der Claude App:

> Loesche den Ordner projects/beispiel-projekt komplett.

Claude löscht ihn, du committest die Änderung in GitHub Desktop.

### 3. Ordner umbenennen

`projects/` heißen für manche lieber `kunden/` oder `baustellen/`. Mach was zu dir passt:

> Benenne den Ordner projects/ in kunden/ um. Pass die CLAUDE.md
> entsprechend an.

Claude macht beides in einem Schritt.

### 4. Eigene Ordner hinzufügen

Brauchst du einen `content/` Ordner für Blog/YouTube? Einen `finanzen/` Ordner? Einfach anlegen, in CLAUDE.md erwähnen.

### 5. Ordner löschen die du nicht nutzt

Wenn du keine Meetings hast: `git rm -r meetings/`. Wenn du keine Tagesnotizen pflegen willst: `git rm -r daily/`. Was du nicht nutzt, soll dich nicht erinnern.

## Vorher / Nachher: ein konkretes Beispiel

### Vorher (frisch geclont)

```
mein-brain/
├── CLAUDE.md (Platzhalter)
├── README.md
├── inbox.md (leer)
├── daily/_template.md
├── projects/_template/
├── projects/beispiel-projekt/
├── reference/example-api.md
├── meetings/_template.md
├── decisions.md
└── CHANGELOG.md
```

### Nachher (nach 30 Minuten Setup von Maria, Freelance-Designerin)

```
maria-brain/
├── CLAUDE.md (Maria, Designerin, drei aktive Kunden)
├── README.md (angepasst)
├── inbox.md (leer)
├── kunden/                          ← projects umbenannt
│   ├── _template/
│   ├── studio-mueller/context.md
│   ├── bakery-frankfurt/context.md
│   └── startup-xyz/context.md
├── reference/
│   ├── tarife.md                   ← eigene Stundensaetze
│   ├── farben-theorie.md
│   └── example-api.md (geloescht spaeter)
├── ideen.md                        ← neuer Ordner fuer Design-Ideen
└── decisions.md
```

Maria hat: projects in kunden umbenannt, Meetings entfernt (sie hat selten welche), daily-Ordner entfernt (sie schreibt kein Daily), reference erweitert mit ihrem Stoff.

Das Template ist jetzt ihr System.

## Template-Updates pullen

Wenn wir das Template updaten (neue Best Practices, neue Beispiele), kannst du die Änderungen zu dir ziehen.

Der einfachste Weg: in der Claude App fragen.

> Schau ins Template-Repo unter github.com/startandconnect/sac-brain-template.
> Welche Dateien wurden seit meinem letzten Update geaendert?
> Schlage mir vor was ich uebernehmen sollte und was nicht (weil ich
> es bewusst angepasst habe).

Claude vergleicht, schlägt vor, du entscheidest, Claude wendet an.

Anschließend in GitHub Desktop committen und pushen.

### Wenn du es manuell machen willst

GitHub Desktop kann das Template auch als zweites "Remote" einbinden. In den Repository-Einstellungen ("Repository Settings → Remotes") ein zusätzliches Remote namens "template" mit der Template-URL hinzufügen. Dann kannst du Updates fetchen und mergen.

Bei Konflikten: Claude App fragen "Löse die Merge-Konflikte in Datei X. Behalte meine Anpassungen wo möglich, übernimm Template-Änderungen wo neutral."

## Was du nicht ändern solltest

- **Die Idee einer CLAUDE.md.** Wenn du die streichst, fehlt Claude der Kontext.
- **Markdown als Format.** Alles andere funktioniert schlechter mit Claude Code.
- **context.md pro Projekt.** Einheitliche Einstiegsdatei ist Gold wert.

## Weiter

Wenn dein Template angepasst ist und das Grundgerüst steht:

- [[claude-md-anleitung|CLAUDE.md richtig schreiben]] - aus dem Platzhalter etwas Brauchbares machen
- [[taegliche-nutzung|Tägliche Nutzung]] - Routinen einführen
- [[advanced|Advanced]] - wenn die Basis läuft
