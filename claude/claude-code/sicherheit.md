---
title: Sicherheit - was nie reingeht
order: 10
excerpt: Welche Daten du nie mit Claude Code teilst und wie du Unfaelle vermeidest
---

# Sicherheit: was nie reingeht

Claude Code ist maechtig. Das heisst auch: ein unvorsichtiger Umgang kann teuer werden. Die wichtigsten Regeln.

## Was nie in Prompts oder Dateien landet

- **API Keys, Passwoerter, Tokens** - auch nicht "zum Testen"
- **Produktions-Kundendaten** - echte Namen, Adressen, E-Mails
- **Finanzdaten** - Kontonummern, IBAN, Karten
- **Vertrauliche Geschaeftsgeheimnisse**

TODO: Wie man diese Daten strukturell fernhaelt (`.env`-Dateien, `.gitignore`, `~/.env.sac` pattern).

## Was tun wenn es doch passiert

- Key rotieren, sofort
- Falls committet: Repo-History pruefen, ggf. History umschreiben
- Bei Kundendaten: Datenschutzvorfall, je nach Schwere melden

TODO: Konkreter Notfallplan.

## Werkzeugseitige Absicherung

- **Permissions:** Claude Code fragt vor Dateiaenderungen. Nicht blind "allow all" drucken.
- **Sandbox-Modus:** fuer riskante Experimente.
- **Git-History:** Aenderungen committen, bevor Claude was umbaut. Dann kannst du zurueckrollen.

TODO: Permissions-System genau beschreiben, Sandbox erklaeren.

## Mindset

Claude Code ist wie ein Praktikant mit Root-Zugriff. Gib ihm nicht das, was du einem Praktikanten auch nicht geben wuerdest.

TODO: Konkrete Beispiele was das heisst.
