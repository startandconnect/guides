---
title: Bestellungen & Rechnungen
order: 5
excerpt: Bestellstatus, Rechnungen, Zahlungen und Stornierung
---

# Bestellungen & Rechnungen

Jede Transaktion in Nexus erzeugt eine Bestellung. Hier behältst du den Überblick über Zahlungsstatus, Rechnungen, Delivery Actions und Erstattungen.

## Bestellübersicht

Unter **Bestellungen** siehst du alle Transaktionen auf einen Blick. Filtere nach Status, Zeitraum, Produkt oder Kunde. Jede Bestellung zeigt:

- Bestellnummer und Datum
- Kunde (Name und E-Mail)
- Produkt(e) und Betrag
- Zahlungsstatus
- Delivery-Status

## Bestellstatus

Jede Bestellung hat einen der folgenden Status:

| Status | Bedeutung |
|--------|-----------|
| **PENDING** | Zahlung steht noch aus |
| **PAID** | Erfolgreich bezahlt |
| **FAILED** | Zahlung fehlgeschlagen |
| **REFUNDED** | Vollständig erstattet |
| **PARTIALLY_REFUNDED** | Teilweise erstattet |
| **CANCELED** | Storniert (vor Zahlung) |
| **EXPIRED** | Zahlungsfrist abgelaufen |

:::info[Hinweis]
Bei Abo-Bestellungen bezieht sich der Status auf die initiale Zahlung. Folge-Zahlungen siehst du in der Zahlungshistorie der Bestellung oder im Abo-Bereich.
:::

## Bestelldetails

Klicke auf eine Bestellung für die vollständige Ansicht:

- **Positionen** - Alle gekauften Produkte mit Einzelpreisen, Rabatten und Gesamtbetrag
- **Rechnungen** - Automatisch erstellte Rechnungen als PDF. Enthalten deine Firmendaten und sind bereit für die Buchhaltung
- **Zahlungen** - Stripe-Zahlungsdetails mit Payment Intent ID
- **Delivery-Status** - Welche Delivery Actions ausgeführt wurden und welche noch ausstehen
- **Gutschein** - Falls ein Coupon eingelöst wurde, mit Rabattbetrag

## Stornierung und Rückerstattung

Du hast zwei Optionen:

1. **Stornieren** - Bestellung abbrechen (nur bei PENDING möglich)
2. **Erstatten** - Geld zurück an den Kunden (voll oder teilweise)

Die Erstattung wird über Stripe abgewickelt. Der Bestellstatus wechselt automatisch auf REFUNDED oder PARTIALLY_REFUNDED. Wurde eine Delivery Action ausgelöst (z.B. Instanz provisioniert), läuft der zugehörige Rückerstattungs-Trigger.

:::tip[Tipp]
Bei Teilerstattungen gibst du den Betrag manuell ein. Das ist praktisch, wenn du z.B. nur ein Produkt aus einer Bestellung erstatten möchtest.
:::

## Technische Details

Jede Bestellung hat eine eindeutige **Bestell-ID** und eine lesbare **Bestellnummer**. Für API-Integrationen und Webhooks nutzt du die Bestell-ID. Die Bestellnummer eignet sich für die Kundenkommunikation.

Rechnungen werden automatisch generiert und sind im Kundenportal für den Kunden abrufbar. Unter **Einstellungen > Rechnungen** konfigurierst du deine Firmendaten, Steuersätze und das Rechnungslayout.
