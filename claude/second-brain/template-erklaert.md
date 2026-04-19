---
title: Das Template erklärt
order: 7
excerpt: Was steckt im Second Brain Template, warum so und wie du es an dich anpasst
---

# Das Template erklärt

Das Second Brain Template ist kein starrer Rahmen, sondern ein durchdachter Startpunkt. Es funktioniert für Studierende, Angestellte und Selbstständige - beim Setup passt Claude die Struktur an deinen Typ an.

:::tip[Template jetzt laden]
[Second Brain Template herunterladen (ZIP, 30 KB)](https://startandconnect.com/api/media-library/files/cmo6dm9fg00ax4bmwgf9r83t1/second-brain-template.zip)
:::

## Was drin ist

Nach dem Entpacken hast du folgende Struktur:

```
second-brain-template/
├── CLAUDE.md                ← vorausgefüllt mit Platzhaltern, Claude füllt beim Onboarding
├── README.md                ← für Menschen
├── SETUP.md                 ← Onboarding-Anleitung für Claude
├── RUNBOOK.md               ← erklärt wie Runbooks funktionieren
├── HAUSAUFGABE.md           ← für Kursteilnehmer - kann gelöscht werden
├── INBOX.md                 ← Quick Capture
├── DECISIONS.md             ← wichtige Entscheidungen
├── CHANGELOG.md             ← strukturelle Änderungen
├── planning/
│   ├── TODAY.md             ← Tagesplanung
│   ├── WEEK.md              ← Wochenfokus
│   ├── MONTH.md             ← Monatsziele
│   └── YEAR.md              ← Jahresziele
├── projects/
│   ├── _template/           ← Kopiervorlage für neue Projekte
│   ├── beispiel-selbststaendig/   ← Beispiel für Solopreneure
│   ├── beispiel-angestellt/       ← Beispiel für Angestellte
│   └── beispiel-student/          ← Beispiel für Studierende
├── reference/
│   ├── _template.md         ← Vorlage für Referenzseiten
│   └── beispiel-referenz.md ← Beispiel einer Referenz
├── sessions/
│   └── _template.md         ← Vorlage für Tages-Session-Logs
├── meetings/
│   └── _template.md         ← Vorlage für Meeting-Notes
├── runbooks/
│   ├── tagesstart.md
│   ├── neues-projekt.md
│   ├── wochenrueckblick.md
│   └── session-pflege.md
├── private/
│   └── _placeholder.md      ← Ordner für private Dateien
└── .gitignore               ← für optionale spätere Git-Nutzung
```

## Warum diese Dateien

### Root-Level Meta-Dateien (CAPS)

**CLAUDE.md** - muss da sein, sonst hat Claude keinen Kontext. Vorausgefüllt als Template mit Platzhaltern - Claude ersetzt sie beim Onboarding mit deinen echten Daten.

**README.md** - für Menschen die dein Repo sehen. Auch für dich in 6 Monaten. Erklärt wofür das Wiki ist.

**SETUP.md** - Anleitung für Claude wie dein Wiki eingerichtet wird. Du sagst Claude: *"Lies SETUP.md und führe das Onboarding durch."*, und Claude übernimmt.

**RUNBOOK.md** - erklärt das Runbook-System. Runbooks sind Anleitungen für wiederkehrende Abläufe.

**HAUSAUFGABE.md** - relevant wenn du Teilnehmer eines Kurses bist. Als Freebie-Nutzer kannst du sie löschen.

**INBOX.md** - Quick Capture. Alles was schnell rein muss, bevor es vergessen wird. Wöchentlich einsortieren.

**DECISIONS.md** - wichtige Entscheidungen mit Datum und Begründung. Wenn du in 6 Monaten wissen willst warum du X entschieden hast.

**CHANGELOG.md** - nur strukturelle Änderungen am Wiki selbst. Nicht jede Mini-Änderung.

### Ordner

**planning/** - vier Zeithorizonte. TODAY für heute, WEEK für die Woche, MONTH für den Monat, YEAR für das Jahr.

**projects/** - deine aktiven Projekte. Einer pro Ordner, mit eigener `context.md` als Einstiegspunkt. Template-Ordner `_template/` als Kopiervorlage. Drei Beispielprojekte (selbstständig, angestellt, student) - Claude behält beim Onboarding nur das passende.

**reference/** - Nachschlagewerk. APIs, Prozesse, Rezepte, Zusammenfassungen. Dinge die du nachschlägst und selten änderst.

**sessions/** - Tages-Logs im Format `YYYY-MM-DD.md`. Was ist heute passiert, was hast du gelernt, was bleibt offen.

**meetings/** - Meeting-Notizen. Teilnehmer, Themen, Entscheidungen, Action Items.

**runbooks/** - Anleitungen für wiederkehrende Abläufe. Vier mitgelieferte: Tagesstart, neues Projekt, Wochenrückblick, Session-Pflege.

**private/** - Privates. Die `.gitignore` sorgt dafür dass der Inhalt nicht committet wird, wenn du später Git nutzt.

## Beispielprojekte anpassen

Nach dem Claude-Onboarding ist nur ein Beispielprojekt übrig - passend zu deinem Typ:

- **Selbstständige:** `projects/beispiel-selbststaendig/` - Newsletter-Automatisierung als Beispiel
- **Angestellte:** `projects/beispiel-angestellt/` - Onboarding-Doku Q2
- **Studierende:** `projects/beispiel-student/` - Hausarbeit Social Media

Du kannst das behaltene Beispiel entweder als Referenz nutzen, anpassen zu einem echten Projekt oder komplett löschen.

## Wie du es anpasst

Das Template ist kein Gesetz. Typische Anpassungen:

### 1. CLAUDE.md personalisieren (Pflicht, macht Claude für dich)

Platzhalter raus, deine echten Informationen rein. Erfolgt automatisch beim Onboarding.

### 2. Beispielprojekt löschen

Sag in der Claude App: *"Lösche den Ordner projects/beispiel-xyz komplett."*

### 3. Ordner umbenennen

`projects/` heissen für manche lieber `kunden/`, `arbeiten/` oder `hausarbeiten/`. Sag in der Claude App: *"Benenne den Ordner projects/ in [neuer Name]/ um und passe die CLAUDE.md entsprechend an."*

### 4. Eigene Ordner hinzufügen

Brauchst du einen `content/`, `finanzen/`, oder `lernen/` Ordner? Einfach anlegen und in der CLAUDE.md erwähnen.

### 5. Ordner löschen die du nicht nutzt

Was du nicht nutzt, soll dich nicht erinnern. Ordner die dir nicht passen: weg damit.

## Was du nicht ändern solltest

- **Die Idee einer CLAUDE.md.** Wenn du die streichst, fehlt Claude der Kontext.
- **Root-Level Meta-Dateien in CAPS.** Konvention damit Claude sie findet.
- **Markdown als Format.** Alles andere funktioniert schlechter mit Claude Code.
- **context.md pro Projekt.** Einheitliche Einstiegsdatei ist Gold wert.

## Weiter

- [[setup|Setup-Anleitung]] - der komplette Einrichtungsprozess
- [[claude-md-anleitung|CLAUDE.md richtig schreiben]] - wie du die zentrale Datei optimierst
- [[taegliche-nutzung|Tägliche Nutzung]] - Routinen die funktionieren
- [[advanced|Advanced]] - wenn die Basis läuft
