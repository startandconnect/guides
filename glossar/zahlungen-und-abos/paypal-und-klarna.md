---
title: PayPal und Klarna
order: 14
excerpt: Alternative Zahlungsmethoden
---

# PayPal und Klarna

Zwei Zahlungsmethoden die Nexus ueber Stripe anbietet. Speziell wichtig fuer deutsche Kunden.

## PayPal

PayPal ist der bekannteste Zahlungsanbieter online. Viele deutsche Kunden haben PayPal-Account und zahlen damit lieber als Kreditkarte einzugeben.

**Vorteile:**
- Bekannt, gewohnt, Vertrauen hoch
- Keine Kreditkarten-Daten bei dir
- Kaeuferschutz (auch ein Nachteil, siehe Chargeback-Analogie)

**Nachteile:**
- **Hoehere Gebuehren**: Stripe-PayPal-Integration 3,3 Prozent + 0,39 Euro
- **Chargeback-freundlich**: PayPal-Disputes werden oft zugunsten des Kaeufers entschieden
- **Abo-kompliziert**: PayPal-Recurring ist nicht so sauber wie Stripe-native-Subscriptions

**Konfiguration**: In Stripe-Dashboard PayPal als Payment-Method aktivieren. Danach in Nexus-Checkout sichtbar.

## Klarna

Schwedischer Anbieter fuer "Kauf auf Rechnung" und Ratenzahlung. In Deutschland sehr populaer.

**Varianten:**
- **Pay Now** - Sofortzahlung, aehnlich Lastschrift
- **Pay in 30** - Rechnung, 30 Tage Zahlungsziel (kostenlos fuer Kunde)
- **Pay Later** - Ratenkauf, 3/6/12 Monate (Kunde zahlt Zinsen)
- **Klarna Financing** - bis 36 Monate Finanzierung

**Gebuehren ueber Stripe**: typisch 4 Prozent + 0,30 Euro. Klarna uebernimmt Forderungs-Risiko - wenn Kunde nicht zahlt, kriegst du trotzdem dein Geld.

**Gut fuer**: hoch-preisige Produkte (ab 200 Euro aufwaerts) wo Ratenzahlung die Conversion hebt.

## Beide in Nexus

Stripe-Panel in Nexus-Admin unter `/manage/settings/stripe`:
- Payment-Methods-Liste
- Toggle pro Methode
- Minimum-Transaktions-Amount pro Methode konfigurierbar

## Welche Methoden anbieten

Nicht alle anbieten. Cognitive-Overhead im Checkout senkt Conversion.

**Faustregel B2C-DE:**
- Kreditkarte
- SEPA-Lastschrift
- PayPal
- Bei Produkten ueber 200 Euro: Klarna

**Faustregel B2B:**
- Kreditkarte
- SEPA
- Rechnungs-Zahlung auf Anfrage (manuell)
- PayPal optional

Wenn du merkst dass eine Methode nie genutzt wird: rausnehmen. Klarer Checkout = bessere Conversion.
