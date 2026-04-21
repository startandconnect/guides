---
title: Stripe
order: 1
excerpt: Der Zahlungsanbieter hinter Nexus
---

# Stripe

Der Zahlungsanbieter mit dem Nexus integriert ist. US-basierte Firma, aber EU-reguliert. Weltmarktfuehrer bei Online-Zahlungen fuer SaaS und digitale Produkte.

## Was Stripe macht

- **Kreditkarten** - Visa, Mastercard, Amex, Discover
- **SEPA-Lastschrift** - Bankeinzug in Europa
- **Apple Pay und Google Pay** - Wallet-Zahlungen
- **Klarna** - Rechnung, Ratenkauf, Pay in 30
- **PayPal** - bei Stripe gebuchte PayPal-Integration
- **Multi-Currency** - >135 Waehrungen
- **Tax** - automatische Steuer-Berechnung

## Wie Nexus Stripe nutzt

- **Stripe Checkout** - das Stripe-Formular in einem Overlay (kein eigener Payment-Code bei dir)
- **Subscriptions** - Stripe verwaltet wiederkehrende Zahlungen
- **Invoices** - Stripe erstellt Rechnungen, Nexus synct und stellt sie als PDF bereit
- **Webhooks** - Stripe benachrichtigt Nexus ueber Zahlungen, Refunds, Disputes
- **Sync** - Stripe-Kunden, -Produkte, -Preise synchronisieren in beide Richtungen

## Gebuehren

- **Card EU**: 1,5 Prozent + 0,25 Euro pro Transaktion
- **Card non-EU**: 2,5 Prozent + 0,25 Euro
- **SEPA**: 0,35 Euro flat pro Transaktion (bis 5 Euro), danach 0,8 Prozent
- **PayPal via Stripe**: 3,3 Prozent + 0,39 Euro
- **Klarna**: typisch 4 Prozent + 0,30 Euro

Nexus nimmt KEINE zusaetzlichen Gebuehren. Du zahlst 99 Euro flat + die Stripe-Gebuehren.

## Test-Mode vs Live-Mode

Stripe hat zwei getrennte Umgebungen:
- **Test** - Test-Karten (4242 4242 4242 4242), keine echte Zahlung
- **Live** - echtes Geld

Nexus unterscheidet pro Instance. Meist: Dev-Instance im Test-Mode, Production-Instance im Live-Mode.

## Kompetenz-Grenzen

- **Kein Invoicing-Only** - Stripe ist primaer Card-Payment. Fuer reine Rechnungs-Geschaefte B2B (Ueberweisung) ist Stripe Overkill, aber integriert.
- **Marketplace mit Split-Payments** - moeglich via Stripe Connect, in Nexus noch nicht implementiert.
- **Kassensystem** - fuer Offline-Point-of-Sale gibt's Stripe Terminal, nicht Nexus-relevant.
