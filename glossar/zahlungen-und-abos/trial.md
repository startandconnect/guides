---
title: Trial
order: 8
excerpt: Kostenloser Test-Zeitraum fuer ein Abo
---

# Trial

Kostenloser Test-Zeitraum eines Abos. Typisch 7, 14 oder 30 Tage. Nach Ablauf wird automatisch abgerechnet (ausser Kunde kuendigt vorher).

## Zwei Varianten

**Opt-in** (Kreditkarte noetig)
- Kunde gibt Zahlungsdaten beim Start an
- Nach Trial wird automatisch abgerechnet
- Hoehere Conversion zum Zahler
- Aber: abschreckend, viele steigen wegen "Karte eingeben" gar nicht erst ein

**Opt-out** (keine Kreditkarte noetig)
- Kunde startet ohne Zahlungsdaten
- Vor Ablauf aktiv entscheiden
- Niedriger Conversion
- Aber: mehr Trial-Signups insgesamt

Welche Variante besser: haengt von Zielgruppe, Produkt-Komplexitaet, Verkaufs-Skill ab.

## Trial in Nexus

Pro Produkt konfigurierbar: `trialDays` als Zahl, `requireCardForTrial` als Bool.

## Stripe-Handling

Stripe hat Trial-Feature eingebaut. Subscription wird angelegt mit `trial_period_days`. Waehrend Trial:
- Keine Abrechnung
- Status ist `trialing`
- Customer-Portal zeigt "Trial endet am [Datum]"

Nach Ablauf: Stripe versucht erste Abrechnung automatisch.

## Trial-Extension

Admin kann Trial verlaengern (Goodwill, technische Probleme). Unter `/manage/subscriptions/:id` Option "Trial verlaengern".

## Trial-Abuse

Einzelne Nutzer koennen mehrere Accounts anlegen um wiederholt Trials zu bekommen. Gegenmassnahmen:
- Email-Duplicate-Check (keine Aliases wie user+1@...)
- Kreditkarte-Fingerprint bei Opt-in (derselbe Card-Fingerprint kann nicht nochmal Trial)
- Fraud-Detection via Stripe Radar

Nicht kritisch bei kleinen Trials, wichtig bei teuren Produkten.

## Conversion-Rate nach Trial

- Opt-in-Trial: 40-70 Prozent Conversion (da Karte schon da)
- Opt-out-Trial: 10-25 Prozent

Onboarding-Qualitaet ist der groesste Hebel. Kunden die waehrend Trial den "Aha-Moment" erreichen, konvertieren massiv besser.

## Nexus hat selbst Trial

14 Tage kostenlos, opt-out (keine Kreditkarte). Kunde startet direkt, entscheidet am Ende.
