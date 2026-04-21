---
title: Cohort (Kohorten-Analyse)
order: 9
excerpt: Kunden nach Startzeitpunkt gruppiert analysieren
---

# Cohort (Kohorten-Analyse)

Gruppe von Nutzern, die im selben Zeitraum gestartet sind - und dann ueber die Zeit zusammen betrachtet werden. Kohorten-Analyse ist der Gold-Standard fuer SaaS-Retention.

## Beispiel

- Januar-Kohorte: 50 neue Kunden in Januar
- Februar-Kohorte: 70 neue Kunden in Februar

Nach 6 Monaten schaust du:
- Wie viele Januar-Kunden sind noch aktiv?
- Wie viele Februar-Kunden sind noch aktiv?

So siehst du: bessern sich deine Produkte / Onboarding / Pricing? Haelst du neuere Kohorten besser?

## Warum wichtig

Einfach "100 aktive Kunden" zu zaehlen, verdeckt Probleme. Wenn 30 Prozent jeden Monat churnen und 30 Prozent neu dazukommen: sieht stabil aus, ist aber ein Fass ohne Boden.

Kohorten-Analyse zeigt: wie gut haelst du Kunden ueber die Zeit, pro Start-Zeitpunkt.

## Was man damit misst

- **Retention-Kurve** - welcher Prozentsatz bleibt nach X Monaten aktiv
- **LTV pro Kohorte** - verlaeuft der LTV besser oder schlechter ueber die Zeit?
- **Pricing-Impact** - hat Preis-Erhoehung die September-Kohorte geschadet?
- **Feature-Impact** - seit Feature X besser/schlechter?

## Darstellung

Typisch als Matrix:

| Kohorte | M0 | M1 | M2 | M3 | M6 | M12 |
|---|---|---|---|---|---|---|
| Jan | 100% | 70% | 55% | 45% | 35% | 25% |
| Feb | 100% | 75% | 60% | 50% | 40% | 30% |

Je weiter rechts und je flacher die Kurve - je besser.

## Tools

Nexus baut Cohort-Analytics nicht selber, aber in den Analytics-Export kannst du CSV ziehen und in Google Sheets oder Amplitude auswerten.
