---
title: SCA und 3D Secure
order: 12
excerpt: Zwei-Faktor-Authentifizierung bei Zahlungen
---

# SCA (Strong Customer Authentication)

EU-Regulierung (PSD2, seit 2019) die bei Online-Zahlungen oft eine zweite Authentifizierung verlangt. Schutz vor Kreditkarten-Betrug.

## Was das heisst

Bei einer Karten-Zahlung im Netz pruefen:
- **Wissen** - Passwort oder PIN
- **Besitz** - Handy (fuer SMS-TAN oder App)
- **Biometrie** - Fingerprint, Face ID

Mindestens zwei davon. Standard: Bank-App bestaetigen oder SMS-Code eingeben.

## 3D Secure (3DS)

Technische Umsetzung von SCA bei Kreditkarten. Heisst offiziell "3-Domain Secure" (Karteninhaber, Bank, Haendler = 3 Domains). Umbenannt in Marketing als "Verified by Visa" / "Mastercard SecureCode" / "American Express SafeKey".

3DS Version 2 ist aktuell (3DS1 ist deprecated). Liefert User-Experience im Bank-App-Frontend statt als Popup.

## Ausnahmen

Keine SCA noetig bei:
- **Transaktionen unter 30 Euro** (bis 5x in Folge, dann doch SCA)
- **Recurring-Subscriptions** (wenn initiales Setup SCA hatte)
- **Merchant-Initiated** (Abo-Zahlungen durch dich, nicht durch Kunde getriggert)
- **Low-Risk-Transactions** (von Bank bestimmt, oft kleine regelmaessige Betraege)

## Fuer Nexus

Du musst nichts manuell tun. Stripe handled SCA automatisch:
- Beim initialen Abo-Setup: 3DS-Challenge dem Kunden zeigen
- Future-Zahlungen ohne SCA (wegen Merchant-Initiated-Exemption)
- Bei Hoch-Betraegen: nochmal SCA

Wenn Kunde SCA-Challenge scheitert, bleibt die Zahlung in "requires_action". Nexus informiert Kunden via Email.

## Auswirkung

Zahlungen dauern manchmal laenger (Kunde muss App oeffnen). Conversion-Rate fallt kurzzeitig wenn SCA initial eingefuehrt wurde - ist aber laengst Normal-Zustand.

## Wichtig bei Trial-Start

Beim Trial (Karte-angeben-aber-noch-nicht-abrechnen) kann SCA schon ausgeloest werden. Manche Banken verlangen "authentication" selbst bei 0-Euro-Setup. Rechne damit.

## SEPA braucht keine SCA

SEPA-Lastschrift ist bereits "starkeGnehmigung" weil Kunde Mandat gibt. Deswegen keine zusaetzliche SCA-Huerde - ein Grund warum SEPA-Conversion oft besser als Kreditkarte ist.
