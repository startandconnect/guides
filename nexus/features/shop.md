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

## Produkt anlegen - Schritt für Schritt

So legst du ein neues Produkt in Nexus an:

1. **Navigiere zu Manage > Produkte** und klicke auf **Neues Produkt**
2. **Titel und Beschreibung** eingeben - der Titel erscheint im Shop, im Checkout und auf Rechnungen. Die Beschreibung wird auf der Produktseite und im Checkout angezeigt
3. **SKU vergeben** (optional) - eine interne Artikelnummer für deine Verwaltung
4. **Produkttyp wählen** - PRODUCT, EVENT, BUNDLE oder HOSTING (siehe Produkttypen oben). Der Typ bestimmt, welche Optionen dir danach zur Verfügung stehen
5. **Produktbilder hochladen** - das Featured Image wird als Hauptbild im Shop und Checkout verwendet. Zusätzlich kannst du eine Galerie mit mehreren Bildern anlegen
6. **Preis hinzufügen** - wähle zwischen Einmalkauf oder Abo. Bei Abos legst du das Intervall fest (WEEKLY, MONTHLY, HALF_YEARLY, YEARLY). Du kannst mehrere Preise pro Produkt anlegen
7. **Trial Days setzen** (optional) - gib die Anzahl der kostenlosen Testtage ein, falls du eine Testphase anbietest
8. **Kategorie zuweisen** - damit erscheint das Produkt im richtigen Filter im Product-Grid auf deiner Website
9. **Status auf ACTIVE setzen** - erst dann ist das Produkt im Shop sichtbar. Lass es auf DRAFT, solange du noch daran arbeitest
10. **Speichern** - dein Produkt ist jetzt live

:::tip[Tipp]
Bereite alle Produktbilder im Voraus vor. Empfohlen: quadratisches Featured Image (mindestens 800x800 px) und Galerie-Bilder im gleichen Seitenverhältnis.
:::

## Erfolgsseite und Abbruchseite

### Erfolgsseite

Nach einem erfolgreichen Kauf wird der Kunde automatisch auf die Erfolgsseite weitergeleitet. Diese Seite bestätigt den Kauf und gibt dem Kunden die nächsten Schritte.

- **Individuelle Erfolgsnachrichten** kannst du pro Produkt konfigurieren. Gehe dazu auf das Produkt und öffne den Bereich **After-Sales**
- **Template-Variablen** stehen dir in der Erfolgsnachricht zur Verfügung, z.B. Kundenname, Produktname und Bestellnummer. So personalisierst du die Nachricht
- **HTML Override** - für eine komplett eigene Erfolgsseite kannst du eigenes HTML schreiben und das Standard-Layout überschreiben

### Abbruchseite

Wenn der Kunde den Checkout abbricht (z.B. den Browser schließt oder auf "Abbrechen" klickt), wird er auf die Abbruchseite geleitet.

- Auch diese Seite lässt sich über **HTML Override** anpassen
- Baue einen klaren Call-to-Action ein, der den Kunden zurück zum Produkt führt

:::tip[Tipp]
Nutze die Abbruchseite als Chance: Biete einen Rabattcode an oder erkläre nochmal die wichtigsten Vorteile deines Produkts.
:::

## Produkt-Landing-Page

Jedes Produkt kann eine eigene Landing Page haben, die du unabhängig von deiner Shop-Übersicht gestaltest.

- **Konfiguration:** Öffne das Produkt und wechsle zum Bereich **Landing Page**
- **Hero Section** - großer Header mit Titel, Untertitel und Hintergrundbild
- **Feature-Abschnitte** - stelle die wichtigsten Vorteile und Funktionen deines Produkts dar
- **CTA Buttons** - Buttons, die direkt zum Checkout führen
- **Eigener Slug** - jede Produkt-Landing-Page bekommt eine eigene URL (z.B. `/produkte/mein-kurs`), die du frei wählen kannst

:::info[Hinweis]
Die Produkt-Landing-Page ist ideal für Ads und Social-Media-Kampagnen. Teile den direkten Link zur Landing Page, statt auf die allgemeine Shop-Übersicht zu verlinken.
:::

## Stripe-Verbindung

Nexus nutzt Stripe als Zahlungsanbieter. Unter **Einstellungen > Zahlungen** verbindest du deinen Stripe-Account. Danach werden alle Zahlungen, Abos und Erstattungen automatisch synchronisiert.
