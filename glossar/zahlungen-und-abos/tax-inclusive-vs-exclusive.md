---
title: Tax-Inclusive vs Tax-Exclusive
order: 9
excerpt: Steuer im Preis oder obendrauf
---

# Tax-Inclusive vs Tax-Exclusive

Zwei Varianten wie Preise und Steuer angezeigt werden.

## Tax-Inclusive

Preis enthaelt bereits Mehrwertsteuer. Standard fuer B2C-Verkauf in Deutschland.

**Beispiel:** "Dieser Kurs kostet 99 Euro (inkl. 19 Prozent MwSt)". Der Kunde zahlt 99 Euro, du bekommst 83,19 Euro Netto, 15,81 Euro Steuer gehst ans Finanzamt.

## Tax-Exclusive

Preis ist ohne Steuer, Steuer kommt oben drauf. Typisch B2B-USA, gelegentlich auch B2B-EU.

**Beispiel:** "99 Euro + MwSt" = 117,81 Euro Brutto. Rechnung zeigt 99 netto, 18,81 Steuer, 117,81 total.

## Wann welche Variante

**B2C Deutschland/EU**: IMMER inclusive. Preise muessen End-Preise sein (Preisangabenverordnung).

**B2B Deutschland/EU**: exclusive ist ueblich, inclusive aber nicht falsch.

**B2B International mit VAT-ID**: Reverse Charge greift - keine Steuer. Nexus zeigt Netto-Preis, markiert Rechnung als "Steuerschuldnerschaft des Leistungsempfaengers".

**US/ausserhalb EU**: Stripe Tax kann je nach State/Country anders berechnen.

## Pro Produkt in Nexus

`product.taxBehavior` Enum:
- `inclusive` - Standard DE-B2C
- `exclusive` - Steuer kommt oben drauf

Oder auf Portal-Level als Default plus pro Produkt-Override.

## Historischer Bug

Bis v1.3.85 hat Nexus bei tax-inclusive Stripe-Checkouts das `subtotal` (=Netto) falsch auf den Brutto-Wert gesetzt. Fix per `calculateOrderAmountsFromSession()` die heuristisch inclusive-Preise erkennt. Betraf PENDING + EXPIRED Orders primaer, PAID-Orders waren via Invoice-Fallback korrekt.

## Auswirkung auf Reports

Finanz-Reports in Nexus (DATEV-Export) zeigen immer Netto + Steuer getrennt. Egal ob Produkt inclusive oder exclusive ist - intern wird immer aufgesplittet.

## Anzeige-Logik im Checkout

Nexus zeigt je nach User-Land und Produkt-Behavior automatisch passende Preise:
- Deutscher B2C: "99 Euro"
- Deutscher B2B mit Company-Feld: "99 Euro (+ 19 Prozent MwSt)"
- EU B2B mit VAT-ID: "99 Euro (Reverse Charge)"
- Non-EU: "99 Euro"
