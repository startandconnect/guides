---
title: Churn
order: 2
excerpt: Wie schnell deine Kunden wegbrechen
---

# Churn (Churn-Rate)

Anteil der Kunden oder des MRR, der in einem Zeitraum weg ist. Entweder durch aktive Kuendigung oder durch Zahlungsausfall.

**Beispiel:** 100 Kunden Anfang des Monats, 3 kuendigen im Monat = 3 Prozent Monats-Churn.

## Customer Churn vs Revenue Churn

- **Customer Churn**: Anzahl verlorener Kunden / Anfangsbestand
- **Revenue Churn**: verlorener MRR / Anfangs-MRR

Wenn ein grosser Kunde kuendigt, ist Revenue-Churn hoeher als Customer-Churn. Beide Werte sind wichtig - Customer-Churn zeigt Produkt-Qualitaet, Revenue-Churn zeigt wirtschaftliche Auswirkung.

## Net Revenue Churn

Churn minus Expansion. Bei gesunden SaaS-Businesses: Expansion gleicht Churn mehr als aus → Net-Revenue-Churn ist NEGATIV (d.h. negatives Churn = Wachstum ohne Neukunden).

## Richtwerte

| Segment | Gesunder Monats-Churn |
|---|---|
| B2C (Endkunden-Abos) | unter 5 Prozent |
| B2B SMB (kleine Firmen) | unter 3 Prozent |
| B2B Mid-Market | unter 2 Prozent |
| B2B Enterprise | unter 1 Prozent |

Jaehrlicher Churn: 1 Prozent monatlich = ~11 Prozent jaehrlich.

## Ursachen-Analyse

- **Freiwilliger Churn** (Kunde kuendigt aktiv): Produkt-Problem, Preis-Problem, Service-Problem
- **Involuntary Churn** (Zahlungsausfall): Kreditkarte abgelaufen, falsche Bankverbindung. Loesbar mit Dunning-Flow.

Nexus hat Dunning-Retry eingebaut (charge.failed Handler + Kunden-Email bei SEPA-Reversal).

## Wie reduzieren

1. **Onboarding** - Kunden die in Woche 1 "aha-Moment" haben, churnen weniger
2. **Engagement-Tracking** - wer Produkt nicht nutzt, kuendigt bald
3. **Jahresabos foerdern** - laenger locked in, bessere Conversion zu Langzeit-Kunden
4. **Exit-Feedback** - bei Kuendigung fragen wieso, daraus lernen
