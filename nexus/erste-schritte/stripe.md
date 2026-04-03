---
title: Stripe verbinden
order: 5
excerpt: Zahlungen einrichten und Geld empfangen
---

# Stripe verbinden

Nexus nutzt Stripe für alle Zahlungen. Deine Kunden können mit über 100 Zahlungsarten bezahlen: Kreditkarte, SEPA, Klarna, PayPal, Apple Pay, Google Pay und mehr.

## Stripe Account einrichten

1. Gehe zu **Einstellungen > Zahlungen**
2. Klicke auf **Stripe verbinden**
3. Folge dem Stripe-Onboarding (oder logge dich in deinen bestehenden Account ein)
4. Nach der Verbindung erscheint dein Stripe-Status als "Verbunden"

## Test- und Live-Modus

Du kannst zwischen Test- und Live-Modus wechseln:

- **Test-Modus** - Keine echten Zahlungen. Nutze Stripe Test-Karten zum Ausprobieren
- **Live-Modus** - Echte Zahlungen auf dein Konto

:::warning[Erst testen]
Richte deinen Shop im Test-Modus ein und teste den gesamten Kaufprozess, bevor du in den Live-Modus wechselst.
:::

## Stripe Import

Du hast schon Kunden und Produkte in Stripe? Nexus kann sie importieren:

1. Gehe zu **Einstellungen > Zahlungen > Stripe Import**
2. Wähle eine Strategie:
   - **Merge** - Bestehende Daten behalten und mit Stripe synchronisieren
   - **Clean** - Alles löschen und frisch von Stripe importieren
3. Starte den Import

Importiert werden: Kunden, Produkte, Preise und aktive Abos.

## Transaktionsgebühren

Nexus erhebt **0% Transaktionsgebühren**. Du zahlst nur die regulären Stripe-Gebühren (ca. 1,5% + 0,25 Euro pro Transaktion in der EU).

## Zahlungsarten

Welche Zahlungsarten deinen Kunden zur Verfügung stehen, wird in deinem Stripe-Dashboard konfiguriert. Nexus übernimmt automatisch alle aktivierten Zahlungsarten.

Beliebte Optionen:
- Kreditkarte (Visa, Mastercard, AMEX)
- SEPA-Lastschrift
- Klarna (Rechnungskauf, Ratenzahlung)
- PayPal
- Apple Pay / Google Pay

