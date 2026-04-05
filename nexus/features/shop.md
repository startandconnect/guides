---
title: Shop & Produkte
order: 1
excerpt: Produkttypen, Preise, Checkout und Stripe-Anbindung
---

# Shop & Produkte

Nexus ist dein kompletter Shop. Du verkaufst digitale Produkte, Events, Bundles und Hosting-Pakete - direkt über deinen eigenen Checkout auf deiner Domain. Ohne Transaktionsgebühren.

## Produkttypen

Nexus kennt vier Produkttypen, die du je nach Angebot einsetzt:

| Typ | Einsatzgebiet | Beispiel |
|-----|--------------|---------|
| **PRODUCT** | Digitale oder physische Produkte | Online-Kurs, E-Book, Coaching |
| **EVENT** | Veranstaltungen mit Datum | Workshop, Webinar, Meetup |
| **BUNDLE** | Mehrere Produkte zusammen | Starter-Paket mit Kurs + E-Book |
| **HOSTING** | SaaS und Hosting-Instanzen | Managed WordPress, eigene App |

Jedes Produkt hat einen Status: **ACTIVE** (im Shop sichtbar), **DRAFT** (noch in Bearbeitung) oder **ARCHIVED** (nicht mehr verfügbar, bestehende Abos laufen weiter).

## Preise und Abrechnung

Pro Produkt kannst du mehrere Preise anlegen - Einmalkauf und Abos beliebig kombiniert:

- **Einmalkauf** - Kunde zahlt einmal, fertig
- **Abo** - Wiederkehrende Zahlung in vier Intervallen: WEEKLY, MONTHLY, HALF_YEARLY oder YEARLY
- **Trial Days** - Pro Preis individuell konfigurierbar, z.B. 14 Tage kostenlos testen
- **Setup Fee** - Einmalige Gebühr zusätzlich zur ersten Zahlung

:::tip[Tipp]
Lege für ein Produkt sowohl einen monatlichen als auch einen jährlichen Preis an. So können deine Kunden im Checkout selbst wählen - und du bietest beim Jahresabo einen Rabatt an.
:::

## Produkte einrichten

Beim Anlegen eines Produkts konfigurierst du:

1. **Name und Beschreibung** - Wird im Shop und Checkout angezeigt
2. **Bilder** - Produktbilder für Shop und Checkout hochladen
3. **SKU** - Optionale Artikelnummer für deine interne Verwaltung
4. **Kategorie** - Für die Filterung im Produkt-Grid auf deiner Website
5. **Digitale Downloads** - Dateien, die nach dem Kauf im Kundenportal verfügbar sind
6. **Preise** - Einmalkauf, Abo oder beides (siehe oben)

Für **Bundles** wählst du zusätzlich die enthaltenen Produkte aus. Der Kunde kauft das Bundle als ein Produkt und erhält Zugang zu allen Bestandteilen.

**Hosting-Produkte** haben eine Besonderheit: Bei Kauf wird automatisch eine Instanz provisioniert (über Delivery Actions). Bei Kündigung wird sie deprovisioniert.

## Checkout

Dein Checkout läuft auf deiner eigenen Domain - kein Redirect zu externen Plattformen. Das Checkout-Erlebnis umfasst:

- Responsive Design für Desktop und Mobile
- Light und Dark Mode
- Gutscheincode-Eingabe direkt im Checkout
- Testphase-Anzeige ("14 Tage kostenlos testen")
- Vergleichspreis (durchgestrichen)
- Konfigurierbare AGB-Checkbox

:::info[Hinweis]
Nexus erhebt **0% Transaktionsgebühren**. Du zahlst nur die regulären Stripe-Gebühren. Das Geld geht direkt auf dein Konto.
:::

## Stripe-Verbindung

Nexus nutzt Stripe als Zahlungsanbieter. Unter **Einstellungen > Zahlungen** verbindest du deinen Stripe-Account. Danach werden alle Zahlungen, Abos und Erstattungen automatisch synchronisiert.
