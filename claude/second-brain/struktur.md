---
title: Die Struktur
order: 2
excerpt: Ordner, Dateinamen und Konventionen die sich bewährt haben
---

# Die Struktur

Ein gutes Second Brain hat wenige Ordner und klare Regeln. Lieber flach und streng als tief und chaotisch.

## Die Basis-Struktur

```
mein-brain/
├── CLAUDE.md          ← Einstieg für Claude Code
├── README.md          ← Einstieg für Menschen (inkl. dich selbst in 6 Monaten)
├── SETUP.md           ← Onboarding-Anleitung für Claude (einmalig)
├── RUNBOOK.md         ← Erklärung Runbook-System
├── INBOX.md           ← Quick Capture: alles was schnell rein muss
├── DECISIONS.md       ← wichtige Entscheidungen mit Datum und Begründung
├── CHANGELOG.md       ← strukturelle Änderungen am Wiki selbst
├── planning/          ← Zeithorizonte
│   ├── TODAY.md
│   ├── WEEK.md
│   ├── MONTH.md
│   └── YEAR.md
├── sessions/          ← Tages-Logs (YYYY-MM-DD.md)
│   ├── 2026-04-15.md
│   └── 2026-04-16.md
├── projects/          ← Deine Projekte / Aufgaben / Arbeiten
│   ├── projekt-eins/
│   │   └── context.md
│   └── projekt-zwei/
│       └── context.md
├── reference/         ← Nachschlagewerk (APIs, Prozesse, Zusammenfassungen)
│   ├── stripe-api.md
│   └── zitierweise-apa.md
├── meetings/          ← Meeting-Notizen (YYYY-MM-DD-thema.md)
│   └── 2026-04-14-kickoff-kunde-x.md
├── runbooks/          ← Anleitungen für wiederkehrende Abläufe
│   ├── tagesstart.md
│   └── wochenrueckblick.md
└── private/           ← Persönliches, wird bei Git-Nutzung nicht committet
```

Das ist der volle Rahmen. Beim Einrichten reicht weniger als die Hälfte - Claude räumt beim Onboarding auf was du nicht brauchst.

## Die Regeln

### 1. CLAUDE.md ist Pflicht

Die erste Datei. Hier steht was Claude wissen muss. Ohne CLAUDE.md fragst du Claude bei jedem neuen Chat das Gleiche. Mit CLAUDE.md kannst du sofort konkret werden.

### 2. context.md pro Projekt

Jeder Projekt-Ordner hat eine context.md mit Status, Zielen, offenen Punkten. Diese Datei ist der Einstieg fürs Projekt - für dich und für Claude.

```
# Projekt XYZ
**Status:** Aktiv
## Was ist das
## Offene Themen
- [ ] Aufgabe 1
```

### 3. Dateinamen klein und mit Bindestrichen

Gut: `not-alone.md`, `stripe-api.md`, `2026-04-15.md`
Schlecht: `Not Alone.md`, `Stripe API.md`, `Heute.md`

Begründung: konsistent, kein Encoding-Chaos, einheitlich sortierbar.

### 4. Dateinamen auf Englisch, Inhalt auf Deutsch

Dateinamen wie `tagesnotiz-fuer-april.md` sind unübersichtlich. `daily-notes-april.md` (oder einfach `sessions/2026-04-15.md`) ist klar. Inhalt darin ruhig auf Deutsch - das liest Claude problemlos.

### 5. Echter Inhalt, keine Platzhalter

Lieber 3 Zeilen mit echter Information als 3 Seiten "wird noch ergänzt". Wenn du etwas wirklich später ausfüllen willst: `TODO:` Marker setzen, Claude versteht das.

## context.md Variationen

### Eigenes Projekt / Produkt

```
# Mein Produkt

**Status:** In Entwicklung
**Typ:** Eigenes Produkt

## Was ist das
SaaS für X. Zielgruppe Y. Differenzierung Z.

## Aktueller Stand
- Backend: läuft
- Frontend: 60 Prozent
- Marketing: noch nichts

## Ziele
- MVP bis Ende Mai
- Erste 10 Beta-Nutzer im Juni
- Public Launch Juli

## Offene Themen
- [ ] Pricing finalisieren
- [ ] Onboarding-Flow bauen

## Entscheidungen
- 2026-04-10: Stripe statt Lemon Squeezy (bessere DACH-Abdeckung)

## Chronologie
- 2026-04-15: Backend deployed
- 2026-04-12: Stripe-Integration
```

### Kundenprojekt

```
# Kunde XYZ - Website-Relaunch

**Status:** Aktiv
**Typ:** Kundenprojekt
**Kontakt:** Max Mustermann (max@kunde.de)
**Budget:** 8000 EUR fix

## Scope
- Relaunch der bestehenden Website
- Migration auf neuen Tech-Stack
- SEO bleibt erhalten

## Deadline
30. Mai 2026 (Launch geplant)

## Offene Themen
- [ ] Designs vom Kunden bekommen
- [ ] Hosting umziehen

## Risiken
- Kunde liefert Inhalte spät - Puffer einbauen
```

### Lernprojekt

```
# Rust lernen

**Status:** Aktiv
**Typ:** Lernprojekt

## Ziel
In drei Monaten ein kleines Tool in Rust bauen.

## Stand
- Basics durch (Rustlings 50 Prozent)
- Zwei Mini-Projekte gemacht

## Offene Themen
- [ ] Async-Konzepte vertiefen
- [ ] Erstes echtes Projekt anfangen

## Was ich gelernt habe
- 2026-04-12: Ownership macht endlich klick
```

## Was du NICHT machen solltest

### Tiefe Verschachtelung

Schlecht:
```
projects/kunden/2026/q2/relaunch-xyz/phase-1/notes/...
```

Gut:
```
projects/kunde-xyz-relaunch/context.md
```

Mehr als zwei Ebenen tief ist meist schon zu viel. Wenn du tief verschachteln willst, fehlt eine Top-Level-Struktur.

### Generische Ordner

Schlecht: `docs/`, `notes/`, `misc/`, `stuff/`

Gut: `reference/` (klares Was), `meetings/` (klares Was), `projects/` (klares Was)

Wenn du keinen klaren Namen findest, gehört der Inhalt vermutlich in einen bestehenden Ordner oder in `INBOX.md`.

### Daten aus Produktivsystemen kopieren

Niemals in einer Wiki-Datei:

- API Keys, Tokens, Passwörter
- Echte Kundendaten (Namen, Adressen, IBAN)
- Interne Dokumente die unter NDA stehen
- Stripe Customer IDs, interne System-IDs (außer Tests)

### Alles auf einmal aufsetzen

Schlecht: 8 Ordner, 30 Templates, 5 Konventionen am Tag 1 anlegen.
Gut: mit CLAUDE.md + erste context.md anfangen, der Rest entsteht aus Bedarf.

:::tip[Pragmatismus]
Wenn du nach einer Woche merkst "Ordner X nutze ich nie" - weg damit. Struktur ist ein Werkzeug, kein Denkmal.
:::
