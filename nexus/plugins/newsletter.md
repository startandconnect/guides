---
title: Newsletter
order: 4
excerpt: E-Mail-Kampagnen, Sequenzen, Segmente und Double-Opt-In
---

# Newsletter

Versende E-Mail-Kampagnen, baue automatische Sequenzen und segmentiere deine Kontakte. Alles direkt in Nexus - mit DSGVO-konformem Double-Opt-In und vollständigem Engagement-Tracking.

## Voraussetzung: SMTP einrichten

Bevor du Newsletter versenden kannst, brauchst du einen SMTP-Anbieter:

1. Gehe zu **Einstellungen > Plugins > Newsletter**
2. Trage deine SMTP-Daten ein (Host, Port, Benutzername, Passwort)
3. Setze die Absender-Adresse und den Absendernamen
4. Teste die Verbindung mit einer Test-E-Mail

:::info[Hinweis]
**Brevo** (ehemals Sendinblue) oder **Mailgun** sind empfohlene Anbieter. Beide bieten kostenlose Kontingente zum Starten und zuverlässige Zustellung.
:::

## Double-Opt-In (DOI)

Newsletter-Anmeldungen nutzen automatisch Double-Opt-In - das ist rechtlich erforderlich (DSGVO) und in Nexus standardmäßig aktiv:

1. Kunde meldet sich über ein Formular an
2. Nexus sendet eine Bestätigungsmail mit Link
3. Kunde klickt den Bestätigungslink
4. Weiterleitung auf die Bestätigungsseite `/newsletter-confirm/[token]`
5. Ab jetzt ist der Kontakt als **aktiv** markiert und erhält Newsletter

Ohne Klick auf den Bestätigungslink bleibt der Kontakt im Status **pending** und erhält keine Kampagnen.

## Subscriber-Verwaltung

Unter **Newsletter > Subscribers** verwaltest du alle Kontakte:

### Status

| Status | Beschreibung |
|--------|-------------|
| **Aktiv** | Erhält Newsletter und Kampagnen |
| **Abgemeldet** | Hat sich abgemeldet, erhält keine E-Mails mehr |
| **Pending** | Warten auf DOI-Bestätigung |

### Import

Du kannst Kontakte per CSV importieren. Die Datei muss mindestens eine E-Mail-Spalte enthalten. Optional: Vorname, Nachname und weitere Felder.

## Suppression List

Die Suppression List verhindert dass E-Mails an ungültige oder abgemeldete Adressen gesendet werden:

- **Abmeldungen** - Wer sich abmeldet, landet automatisch auf der Suppression List
- **Bounces** - Ungültige Adressen werden automatisch hinzugefügt
- **Re-Subscribe** - Wenn sich ein Kontakt erneut anmeldet, wird die Suppression aufgehoben

Die Suppression List wird automatisch verwaltet. Du musst nichts manuell pflegen.

## Broadcasts (Kampagnen)

Broadcasts sind einmalige E-Mail-Kampagnen:

1. Gehe zu **Newsletter > Broadcasts**
2. Klicke auf **Neuer Broadcast**
3. Wähle ein E-Mail-Template oder erstelle den Inhalt direkt
4. Wähle die Empfänger: ein Segment, eine Liste oder alle aktiven Subscribers
5. Sende sofort oder plane den Versand für einen späteren Zeitpunkt

:::tip[Tipp]
Teste jede Kampagne mit einer Test-E-Mail an dich selbst bevor du sie an alle versendest.
:::

## Segmente

Segmente sind dynamische Empfängergruppen basierend auf Kriterien:

- "Hat in den letzten 30 Tagen gekauft"
- "Hat die letzte Kampagne geöffnet"
- "Ist seit mehr als 6 Monaten Subscriber"

Segmente aktualisieren sich automatisch. Neue Kontakte die die Kriterien erfüllen, werden automatisch hinzugefügt.

## Listen

Listen sind statische Kontaktgruppen:

- Erstelle Listen wie "VIP-Kunden", "Beta-Tester" oder "Webinar-Teilnehmer"
- Füge Kontakte manuell oder per Import hinzu
- Nutze Listen als Empfänger für Broadcasts

## Sequences (Automatische Sequenzen)

Sequences sind automatische E-Mail-Abfolgen die nach einem Trigger starten:

1. Erstelle eine Sequence unter **Newsletter > Sequences**
2. Füge E-Mail-Schritte hinzu mit Wartezeiten dazwischen
3. Definiere den Trigger (z.B. "Nach Newsletter-Anmeldung")

Beispiel einer Willkommens-Sequenz:

- **Tag 0** - Willkommens-E-Mail
- **Tag 3** - Erster Tipp oder Mehrwert
- **Tag 7** - Angebot oder Call-to-Action

Jeder Schritt hat eigene Bedingungen und Wartezeiten.

## Engagement-Tracking

Für jede Kampagne und Sequenz siehst du:

- **Öffnungsrate** - Wie viele Empfänger die E-Mail geöffnet haben
- **Klickrate** - Wie viele auf Links geklickt haben
- **Abmeldungen** - Wie viele sich abgemeldet haben

## E-Mail Log

Jede versendete E-Mail wird im Log protokolliert. Unter **Newsletter > Log** siehst du:

- Empfänger, Betreff und Zeitpunkt
- Status (zugestellt, geöffnet, geklickt, bounced)
- Zugehörige Kampagne oder Sequenz

Das Log hilft dir bei der Fehlersuche wenn E-Mails nicht ankommen.
