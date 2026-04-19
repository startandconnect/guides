---
title: Wann NICHT Claude
order: 2
excerpt: Ehrliche Grenzen - wo andere Werkzeuge besser sind
---

# Wann NICHT Claude

KI ist ein Werkzeug, nicht die Lösung. Diese Seite ist Pflichtlektüre.

## Wenn Determinismus wichtig ist

Steuer-Berechnungen, Buchhaltung, kritische Zahlen. Nimm Code, nicht KI. KI rät gelegentlich falsch, auch bei einfachen Rechnungen.

**Konkrete Beispiele wo das passiert**

- **Mehrwertsteuer-Berechnung in Rechnungen.** Ergebnis muss exakt stimmen. Nimm Buchhaltungssoftware, nicht Claude.
- **Zinsen über mehrere Jahre.** Eine Komma-Stelle Fehler bedeutet Hunderte Euro. Excel oder Code, nicht Claude.
- **Datenbank-Migrationen.** Du willst dass die Logik deterministisch ist. Nicht "wahrscheinlich richtig".
- **Tarif-Berechnungen.** Ein Sales-Mitarbeiter der einem Kunden eine Quote nennt darf sich nicht darauf verlassen dass die KI richtig multipliziert hat.

**Gegenmaßnahme:** wenn du Claude für so was nutzt, lass ein Script schreiben und das Script ausführen. Code rechnet immer richtig.

## Wenn Geschwindigkeit entscheidet

Einfacher Suchen-Ersetzen, simple Regex, bekannte Tastaturkombination. Schneller selbst gemacht als KI-Antwort abgewartet.

**Vergleich an Beispielen**

| Aufgabe | Mensch | Claude |
|---|---|---|
| Wort in Dokument ersetzen | 3 Sekunden | 30 Sekunden |
| Bekannte Datei öffnen | 2 Sekunden | nicht möglich |
| Ein Satz umformulieren wenn du weißt wie | 10 Sekunden | 30 Sekunden |
| Datei umbenennen | 2 Sekunden | nicht nötig |

Faustregel: wenn du die Aufgabe selbst in unter 30 Sekunden machen würdest, mach sie selbst. Sonst vergeudest du mehr Zeit beim Briefen als beim Selbermachen.

**Gegenmaßnahme:** vor jeder Frage an Claude kurz fragen "Mache ich das selbst schneller?"

## Wenn Datenschutz kritisch ist

Gesundheitsdaten, hochsensible Personendaten, Anwaltskanzlei-Akten. Auch bei EU-Hosting ist Zero-Send oft besser. Frag dich: wenn morgen ein Datenleck beim Anbieter wäre - wie schlimm?

**Rechtliche Einordnung**

- **Anthropic ist US-Unternehmen.** Daten gehen in die USA. DSGVO-Konformität ist möglich (AVV mit Anthropic), erfordert aber sauberes Setup.
- **Hochsensible Daten (Gesundheit, Finanzen, Strafregister):** brauchen oft besondere Schutzmaßnahmen die Standard-Cloud-KI nicht bietet.
- **Berufsgeheimnisse (Ärzte, Anwälte, Steuerberater):** strenge Regeln, im Zweifel nicht in fremde KI-Systeme.
- **DSGVO Art. 9 (besondere Kategorien personenbezogener Daten):** vor Verarbeitung in KI-Systemen Rechtsberatung holen.

**Alternativen für sensible Anwendungsfälle**

- **Lokale Modelle:** Llama, Mistral, Qwen. Laufen auf eigenem Rechner, Daten verlassen nie deine Kontrolle. Performance schlechter als Claude, aber für viele Aufgaben ausreichend.
- **EU-gehostete Anbieter:** Aleph Alpha, Mistral mit EU-Hosting. Datenschutz-rechtlich einfacher.
- **Anonymisierung:** echte Daten durch Platzhalter ersetzen bevor sie in die KI gehen.

**Gegenmaßnahme:** für jede Anwendungsdomain einmal sauber durchdenken was darf rein und was nicht. Nicht ad-hoc entscheiden.

## Wenn du ohnehin selbst nachdenken musst

Strategische Entscheidungen, Personalfragen, ethische Abwägungen. KI kann Strukturierung helfen, aber die Entscheidung muss von dir kommen.

**Beispiele für "KI hilft bei der Struktur, aber die Antwort kommt von dir"**

- **Soll ich einen Mitarbeiter entlassen?** KI kann Abwägungspunkte sortieren. Die Entscheidung musst du treffen, nach deinem Wertesystem.
- **Welches Geschäftsmodell soll ich verfolgen?** KI kann Optionen analysieren. Die Entscheidung hängt von dir ab, deinem Risikoprofil, deinen Werten.
- **Soll ich diesen Kunden annehmen?** KI kann Pro/Contra listen. Die Bauchgefühl-Komponente bringst du mit.
- **Wie geht es mir gerade?** KI ist kein Therapeut. Kann helfen Gedanken zu sortieren, ersetzt aber kein echtes Gespräch (mit Mensch oder Profi).

**Gegenmaßnahme:** wenn du merkst du suchst von Claude eine Entscheidung statt einer Strukturierung - kurz innehalten. Was ist die richtige Frage? "Was soll ich tun" → KI rät. "Was sind die wichtigsten Aspekte zu meiner Entscheidung" → KI hilft.

## Wenn du das Problem nicht verstehst

Wenn du nicht weißt was du willst, kann KI es auch nicht wissen. Erst denken, dann prompten.

**Warum das so oft passiert**

- **Du fühlst Unbehagen** und willst eine Antwort. Schneller als das Unbehagen zu verstehen.
- **Du hast einen Termindruck** und glaubst KI würde das Denken abkürzen.
- **Du bist mental erschöpft** und delegierst aus Schwäche statt aus Stärke.

**Typische Anzeichen dass du noch nicht so weit bist zu fragen**

- Du kannst nicht in einem Satz formulieren was du willst
- Du würdest die KI-Antwort nicht erkennen können wenn sie da wäre
- Du fragst die gleiche Frage in 5 Variationen weil keine "passt"
- Du wechselst alle 2 Minuten den Fokus

**Gegenmaßnahme:** weg vom Bildschirm. Spazieren gehen, schreiben (auf Papier), mit jemandem reden. Erst wenn du das Problem in einem Satz beschreiben kannst, ist KI sinnvoll.

## Wann sind wir uns einig: Claude HILFT

Wenn deine Aufgabe folgende Kriterien erfüllt:

- Sie ist klar formulierbar
- Sie ist nicht determiniert (es gibt nicht die eine richtige Antwort)
- Sie betrifft Sprache, Code, Strukturierung, Analyse
- Sie ist nicht kritisch hinsichtlich Genauigkeit oder Datenschutz
- Du würdest sie selbst länger als 5 Minuten brauchen

Dann ist Claude oft das richtige Werkzeug.

:::tip[Ehrliche Selbstprüfung]
Bevor du Claude einschaltest: Frage dich kurz "Könnte ich das in 3 Minuten selber machen?" Wenn ja, mach es selber. Du lernst dabei und bist schneller.
:::
