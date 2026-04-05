---
title: Stripe einrichten
order: 8
excerpt: Stripe Schritt für Schritt verbinden und Zahlungen empfangen
---

# Stripe einrichten

Stripe ist der Zahlungsanbieter hinter Nexus. Über Stripe kannst du Kreditkarten, SEPA, PayPal, Klarna und viele weitere Zahlungsarten akzeptieren. Hier richtest du alles von Null ein.

## Schritt 1: Stripe Account erstellen

Falls du noch keinen Stripe Account hast:

1. Gehe zu [stripe.com](https://stripe.com) und erstelle einen Account
2. Verifiziere deine E-Mail-Adresse
3. Fülle die Geschäftsdaten aus:
   - Unternehmensform (Einzelunternehmer, GmbH, etc.)
   - Geschäftsadresse
   - Bankverbindung für Auszahlungen
   - Steuernummer
4. Warte auf die Verifizierung (dauert meist 1-2 Werktage)

:::info[Hinweis]
Du kannst Stripe im Test-Modus sofort nutzen, auch bevor die Verifizierung abgeschlossen ist. Echte Zahlungen sind erst nach erfolgreicher Verifizierung möglich.
:::

## Schritt 2: API Keys kopieren

Nexus braucht deine Stripe API Keys, um Zahlungen zu verarbeiten:

1. Gehe in dein Stripe Dashboard zu **Developers > API Keys**
2. Du siehst zwei Keys:
   - **Publishable Key** (beginnt mit `pk_live_` oder `pk_test_`)
   - **Secret Key** (beginnt mit `sk_live_` oder `sk_test_`)
3. Kopiere beide Keys

:::warning[Wichtig]
Teile deinen Secret Key niemals öffentlich. Er gibt vollen Zugriff auf dein Stripe-Konto. Trage ihn nur in Nexus ein und sende ihn nicht per E-Mail oder Chat.
:::

## Schritt 3: In Nexus eintragen

Verbinde Stripe mit deiner Nexus-Instanz:

1. Gehe zu **Einstellungen > Zahlungen > Stripe**
2. Trage den **Publishable Key** ein
3. Trage den **Secret Key** ein
4. Klicke auf **Verbinden**
5. Der Status wechselt auf "Verbunden"

## Schritt 4: Webhook konfigurieren

Webhooks informieren Nexus über Zahlungsereignisse (Kauf abgeschlossen, Abo gekündigt, etc.):

1. Nexus zeigt dir nach der Verbindung eine **Webhook URL** an
2. Kopiere diese URL
3. Gehe in Stripe zu **Developers > Webhooks > Add Endpoint**
4. Füge die URL ein
5. Wähle die Events aus, die Nexus empfangen soll (Nexus zeigt dir die Liste der benötigten Events an)
6. Speichere den Webhook
7. Kopiere das **Webhook Secret** (beginnt mit `whsec_`) und trage es in Nexus ein

:::tip[Tipp]
Nexus zeigt dir die genaue Webhook URL und die benötigten Events an. Folge einfach den Anweisungen auf der Einstellungsseite.
:::

## Schritt 5: Zahlungsmethoden aktivieren

Lege fest, wie deine Kunden bezahlen können:

1. Gehe in Stripe zu **Settings > Payments > Payment Methods**
2. Aktiviere die gewünschten Zahlungsarten:

| Zahlungsart | Verbreitung | Gebühren (ca.) |
|-------------|------------|---------------|
| Kreditkarte | Weltweit | 1,5% + 0,25 Euro |
| SEPA-Lastschrift | DACH | 0,35 Euro |
| PayPal | Weltweit | 2,49% + 0,35 Euro |
| Klarna | DACH | 2,49% + 0,25 Euro |
| Apple/Google Pay | Weltweit | wie Kreditkarte |

3. Nexus übernimmt automatisch alle in Stripe aktivierten Zahlungsarten

## Schritt 6: Test-Modus nutzen

Bevor du echte Zahlungen annimmst, teste alles im Test-Modus:

1. Nutze die Stripe Test-Keys (beginnen mit `pk_test_` und `sk_test_`)
2. Erstelle ein Testprodukt in Nexus
3. Führe einen Testkauf durch mit diesen Test-Kartennummern:

| Karte | Nummer | Ergebnis |
|-------|--------|---------|
| Visa (Erfolg) | 4242 4242 4242 4242 | Zahlung erfolgreich |
| Visa (Abgelehnt) | 4000 0000 0000 0002 | Zahlung abgelehnt |
| SEPA | DE89 3704 0044 0532 0130 00 | SEPA-Lastschrift |

Verwende ein beliebiges Ablaufdatum in der Zukunft und eine beliebige CVC.

## Schritt 7: Live-Modus aktivieren

Wenn alles im Test-Modus funktioniert:

1. Gehe in Nexus zu **Einstellungen > Zahlungen > Stripe**
2. Ersetze die Test-Keys durch die Live-Keys
3. Aktualisiere den Webhook (erstelle einen neuen mit der Live-URL oder passe den bestehenden an)
4. Führe eine echte Testzahlung durch (z.B. 1 Euro Produkt)
5. Prüfe, ob der Betrag in deinem Stripe Dashboard erscheint

## Schritt 8: Bestehende Kunden importieren

Du hast bereits Kunden und Abos in Stripe? Importiere sie:

1. Gehe zu **Einstellungen > Zahlungen > Stripe Import**
2. Wähle eine Import-Strategie:
   - **Merge:** Bestehende Nexus-Daten behalten, Stripe-Daten dazufügen
   - **Clean:** Alles in Nexus löschen, komplett von Stripe importieren
3. Starte den Import
4. Nexus importiert: Kunden, Produkte, Preise, aktive Abos

:::info[Hinweis]
Der Import kann bei vielen Daten einige Minuten dauern. Du erhältst eine Benachrichtigung, wenn er abgeschlossen ist. Bestehende Abos laufen nahtlos weiter.
:::
