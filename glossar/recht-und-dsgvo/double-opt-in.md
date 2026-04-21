---
title: Double-Opt-In
order: 2
excerpt: Zwei-Stufen-Bestaetigung fuer Newsletter
---

# Double-Opt-In (DOI)

Zwei-Stufen-Anmeldung fuer Newsletter oder Mailinglisten. Pflicht in Deutschland fuer rechtssichere Email-Werbung.

## Der Ablauf

1. **Anmeldung** - Kunde gibt Email an auf deiner Seite
2. **Bestaetigungs-Email** - Kunde bekommt Email mit Bestaetigungs-Link
3. **Klick auf Link** - erst jetzt ist er wirklich abonniert
4. **Nachweis** - du speicherst Anmelde-Zeit, IP, Link-Klick-Zeit

Vor Klick: NICHT abonniert, keine Werbemails schicken.

## Warum Pflicht

- **Anti-Missbrauch** - verhindert dass jemand fremde Emails angibt und die dann Spam bekommen
- **Nachweis fuer dich** - wenn Abmahnung kommt, hast du dokumentierte Zustimmung
- **DSGVO-konform** - freiwillige und aktive Einwilligung

## Was ohne DOI passiert

- Abmahnung moeglich (Anwaelte spezialisieren sich darauf)
- Geldstrafen von 500 bis mehrere tausend Euro pro Fall
- Reputations-Schaden

## Nexus Newsletter-Plugin

Hat DOI eingebaut:
- Anmelde-Formular auf der Website
- Automatische Confirmation-Email mit unique Token
- Confirmation-Page `/newsletter-confirm/:token`
- Erst nach Klick wird Contact in Subscriber-Segment gepackt
- Timing + IP werden protokolliert

## DOI-Ausnahmen

- **Bestandskunden-Regel** - wenn der Empfaenger bei dir gekauft hat, darfst du ihm auch ohne DOI Werbung fuer aehnliche Produkte schicken (Paragraph 7 Abs 3 UWG). Muss bei jeder Mail die Moeglichkeit zum Widerspruch geben.
- **Transaktionale Mails** - Bestellbestaetigung, Versand-Info, Rechnung - kein DOI noetig, das sind Vertrags-Mails nicht Werbung

## Single-Opt-In

USA-ueblich. Eine Anmeldung reicht, kein Bestaetigungs-Link. In Deutschland nicht rechtssicher fuer Werbung.

## Confirmed-Opt-In

Ist eigentlich dasselbe wie DOI - beide Begriffe werden synonym verwendet.

## Nachweis-Pflicht

Im Zweifelsfall musst du beweisen dass der Kunde zugestimmt hat. Nexus speichert pro Contact:
- Anmelde-Zeitpunkt
- IP-Adresse
- DOI-Klick-Zeitpunkt
- Source (welches Formular)

Das reicht typisch vor Gericht.
