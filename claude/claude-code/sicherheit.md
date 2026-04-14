---
title: Sicherheit - was nie reingeht
order: 10
excerpt: Welche Daten du nie mit Claude Code teilst und wie du Unfälle vermeidest
---

# Sicherheit: was nie reingeht

Claude Code ist mächtig. Das heißt auch: ein unvorsichtiger Umgang kann teuer werden. Die wichtigsten Regeln.

## Was nie in Prompts oder Dateien landet

- **API Keys, Passwörter, Tokens** - auch nicht "zum Testen"
- **Produktions-Kundendaten** - echte Namen, Adressen, E-Mails
- **Finanzdaten** - Kontonummern, IBAN, Karten
- **Vertrauliche Geschäftsgeheimnisse**

TODO: Wie man diese Daten strukturell fernhält (`.env`-Dateien, `.gitignore`, `~/.env.sac` pattern).

## Was tun wenn es doch passiert

- Key rotieren, sofort
- Falls committet: Repo-History prüfen, ggf. History umschreiben
- Bei Kundendaten: Datenschutzvorfall, je nach Schwere melden

TODO: Konkreter Notfallplan.

## Werkzeugseitige Absicherung

- **Permissions:** Claude Code fragt vor Dateiänderungen. Nicht blind "allow all" drücken.
- **Sandbox-Modus:** für riskante Experimente.
- **Git-History:** Änderungen committen, bevor Claude was umbaut. Dann kannst du zurückrollen.

TODO: Permissions-System genau beschreiben, Sandbox erklären.

## Mindset

Claude Code ist wie ein Praktikant mit Root-Zugriff. Gib ihm nicht das, was du einem Praktikanten auch nicht geben würdest.

TODO: Konkrete Beispiele was das heißt.
