---
title: Coupon
order: 5
excerpt: Rabattcodes und Gutscheine
---

# Coupon (Gutschein / Rabattcode)

Rabatt-Code mit festem Betrag, Prozent-Wert oder als kostenloser Zugang. Kann einmalig oder wiederkehrend gelten.

## Varianten

**Betrag** - fester Rabatt in Waehrung: `FRUEHBUCHER` = 20 Euro Rabatt.

**Prozent** - prozentualer Rabatt: `SOMMER10` = 10 Prozent Rabatt.

**Freebie** - kostenloser Zugang: `PRESSE` = 100 Prozent Rabatt, also gratis.

## Einstellungen

Pro Coupon konfigurierbar:

- **Max Uses** - wie oft insgesamt einloesbar (1, 100, unbegrenzt)
- **Max Uses per Customer** - Anti-Abuse-Schutz
- **Valid From / Valid Until** - Zeitfenster
- **Eligible Products** - fuer welche Produkte
- **Eligible Customers** - fuer bestimmte Kunden / Segmente

## Duration (bei Subscriptions)

Coupon-Verhalten bei Abos:

- **once** - einmaliger Rabatt auf erste Rechnung
- **repeating** - fuer X Monate (z.B. 3 Monate lang 20 Prozent rabattiert)
- **forever** - auf jede zukuenftige Rechnung

## SAC-Beispiel

Startup-Rabatt `STARTUP49`:
- Duration: repeating
- Duration in months: 12
- Amount: 50 Euro off
- Effekt: Kunde zahlt 12 Monate lang 49 Euro statt 99 Euro

Kombiniert mit Jahres-Rabatt waere der Preis weiter gedrueckt.

## Technisch

Nexus synchronisiert Coupons mit Stripe. Einlosung am Checkout reduziert den Preis und wird bei Abo-Zahlungen auch fuer Folge-Rechnungen angewandt (bei repeating/forever Duration).

## Coupon-Tracking

Jede Einloesung wird in der CouponUsage-Tabelle erfasst: welcher Kunde, welches Datum, welche Order. Admin sieht Auswertung im Coupon-Detail.

## Coupon-Anzeige im Checkout

Standard: Feld "Gutschein-Code eingeben" im Checkout-Overlay. Automatisch angewandte Coupons (z.B. via URL-Parameter) sind auch moeglich.

## Bug-Historie

`Coupon.usedCount` wurde bei Order-DELETE nicht dekrementiert - Coupons konnten vorzeitig als "aufgebraucht" markiert werden. Gefixt v1.3.45.
