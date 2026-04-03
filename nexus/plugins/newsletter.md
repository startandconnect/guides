---
title: Newsletter
order: 4
excerpt: E-Mail-Kampagnen und automatische Sequenzen
---

# Newsletter

Versende E-Mail-Kampagnen, baue automatische Sequenzen und segmentiere deine Kontakte. Alles direkt in Nexus.

## Voraussetzung: SMTP einrichten

Bevor du Newsletter versenden kannst, brauchst du einen SMTP-Anbieter:

1. Gehe zu **Einstellungen > Plugins > Newsletter**
2. Trage deine SMTP-Daten ein (Host, Port, Benutzername, Passwort)
3. Teste die Verbindung

:::info[Empfohlene Anbieter]
**Brevo** (ehemals Sendinblue) oder **Mailgun** sind gute Optionen. Beide bieten kostenlose Kontingente zum Starten.
:::

## Kampagne erstellen

1. Gehe zu **Newsletter > Kampagnen**
2. Klicke auf **Neue Kampagne**
3. Wähle Empfänger (Segment oder Liste)
4. Erstelle den Inhalt (HTML oder Text)
5. Sende sofort oder plane den Versand

## Segmente & Listen

Organisiere deine Empfänger:

- **Listen** - Statische Gruppen (z.B. "VIP-Kunden", "Beta-Tester")
- **Segmente** - Dynamische Gruppen basierend auf Regeln (z.B. "Hat in den letzten 30 Tagen gekauft")

## Automatische Sequenzen

Erstelle E-Mail-Serien die automatisch versendet werden:

1. Willkommens-E-Mail (sofort nach Anmeldung)
2. Tipp #1 (nach 3 Tagen)
3. Angebot (nach 7 Tagen)

Jeder Schritt hat eigene Bedingungen und Wartezeiten.

## Double Opt-In

Newsletter-Anmeldungen nutzen automatisch Double Opt-In:

1. Kunde meldet sich an
2. Bestätigungs-E-Mail wird versendet
3. Erst nach Klick auf den Bestätigungslink wird der Kontakt aktiv

Das ist rechtlich erforderlich (DSGVO) und in Nexus standardmäßig aktiv.

## Tracking

Für jede Kampagne siehst du:

- Zustellrate
- Öffnungsrate
- Klickrate
- Abmeldungen
