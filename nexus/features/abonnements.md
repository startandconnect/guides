---
title: Abonnements
order: 6
excerpt: Abo-Verwaltung, Billing-Intervalle und Stripe-Sync
---

# Abonnements

Abos sind der Kern vieler digitaler Geschäftsmodelle. Nexus verwaltet den kompletten Abo-Lifecycle - von der Trial-Phase über die wiederkehrende Abrechnung bis zur Kündigung. Alles synchron mit Stripe.

## Abo-Übersicht

Unter **Abonnements** siehst du alle aktiven und beendeten Abos. Jedes Abo zeigt:

- Kunde (Name und E-Mail)
- Produkt und Preisvariante
- Aktueller Status
- Nächstes Abrechnungsdatum
- Bisher gezahlter Gesamtbetrag
- Startdatum und ggf. Trial-Ende

## Billing-Intervalle

Nexus unterstützt vier Abrechnungsintervalle:

| Intervall | Zyklus |
|-----------|--------|
| **WEEKLY** | Wöchentliche Abrechnung |
| **MONTHLY** | Monatliche Abrechnung |
| **HALF_YEARLY** | Alle 6 Monate |
| **YEARLY** | Jährliche Abrechnung |

Das Intervall wird beim Preis festgelegt (unter Produkt > Preise). Pro Produkt kannst du mehrere Intervalle anbieten - der Kunde wählt im Checkout.

## Trial Days

Jeder Abo-Preis kann eine kostenlose Testphase haben. Während der Trial Days:

- Der Kunde hat vollen Zugang zum Produkt
- Es wird noch nicht abgerechnet
- Im Kundenportal sieht der Kunde, wann die Trial endet
- Nach Ablauf startet automatisch die erste Zahlung

:::tip[Tipp]
Trial Days lassen sich pro Preisvariante unterschiedlich setzen. So bietest du z.B. beim Monatsabo 14 Tage Trial an, beim Jahresabo 30 Tage.
:::

## Abo-Status

Jedes Abo durchläuft verschiedene Status:

- **ACTIVE** - Läuft und wird regelmäßig abgerechnet
- **TRIALING** - In der kostenlosen Testphase
- **PAST_DUE** - Zahlung fehlgeschlagen, Retry läuft
- **CANCELED** - Gekündigt, läuft bis zum Ende der bezahlten Periode
- **EXPIRED** - Abo ist ausgelaufen
- **UNPAID** - Alle Zahlungsversuche fehlgeschlagen

## Stripe-Sync

Nexus synchronisiert alle Abo-Daten in Echtzeit mit Stripe:

- Statusänderungen werden sofort übernommen
- Zahlungen erscheinen automatisch in der Zahlungshistorie
- Kündigungen über Stripe werden in Nexus reflektiert
- Manuelle Änderungen in Stripe (z.B. Preisanpassungen) werden synchronisiert

:::warning[Wichtig]
Ändere Abos bevorzugt über Nexus, nicht direkt in Stripe. So stellst du sicher, dass Delivery Actions korrekt ausgelöst werden.
:::

## Kündigung

Du kannst ein Abo jederzeit kündigen - entweder sofort oder zum Ende der aktuellen Periode. Auch deine Kunden können über das Kundenportal selbst kündigen.

Bei Kündigung werden die konfigurierten Delivery Actions am Produkt für den Trigger **Bei Kündigung** ausgeführt (z.B. Abschiedsmail senden, Instanz deprovisionieren). Zusaetzlich feuern die Automation-Trigger `SUBSCRIPTION_CANCELED` und `ACCESS_REVOKED`, sodass du im [Automations-System](./automatisierung.md) eigene Rules darauf bauen kannst (z.B. Win-Back-Sequenz starten).

## Rechnungs- und Zahlungshistorie

In den Abo-Details findest du:

- **Rechnungshistorie** - Alle Rechnungen, die für dieses Abo erstellt wurden
- **Zahlungshistorie** - Jede einzelne Zahlung mit Datum, Betrag und Status
- **Bisher gezahlt** - Gesamtsumme aller erfolgreichen Zahlungen

So hast du pro Abo den kompletten finanziellen Überblick.
