---
title: Erstes Produkt anlegen
order: 4
excerpt: In wenigen Minuten verkaufsbereit
---

# Erstes Produkt anlegen

## Produkt erstellen

1. Gehe zu **Produkte** im Seitenmenü
2. Klicke auf **Neues Produkt**
3. Fülle die Grunddaten aus:
   - **Name** - z.B. "Online-Kurs: Marketing Basics"
   - **Preis** - z.B. 49 Euro
   - **Beschreibung** - Was bekommt der Käufer?

## Produkttypen

| Typ | Beschreibung | Beispiel |
|-----|-------------|---------|
| Einmalzahlung | Einmal kaufen, dauerhaft Zugang | Download, Kurs |
| Abo (monatlich) | Wiederkehrende Zahlung | Membership, SaaS |
| Abo (jährlich) | Jahresabo mit Rabatt | Premium-Zugang |

## Preise konfigurieren

Unter **Preise** kannst du mehrere Preisvarianten anlegen:

- **Monatlich** und **Jährlich** als Toggle im Checkout
- **Testphase** - z.B. 14 Tage kostenlos testen
- **Setup-Gebühr** - Einmalige Gebühr zusätzlich zum Abo
- **Vergleichspreis** - Durchgestrichen angezeigt (Anker-Effekt)

## Checkout

Jeder Produkt hat eine eigene Checkout-URL. Du kannst sie:

- Direkt verlinken: `deinedomain.de/p/produkt-slug`
- In deine Website einbauen mit `#checkout:produkt-slug`
- Als Button auf Landing Pages nutzen

:::info[Stripe verbinden]
Bevor Kunden kaufen können, musst du Stripe verbinden. Gehe zu **Einstellungen > Zahlungen** und folge den Anweisungen.
:::

## Automatische Auslieferung

Nach dem Kauf passiert automatisch:

- Kunde bekommt eine Bestellbestätigung per E-Mail
- Zugang zum Kundenportal wird freigeschaltet
- Downloads sind sofort verfügbar
- Delivery Actions werden ausgeführt (E-Mails, Webhooks, etc.)

