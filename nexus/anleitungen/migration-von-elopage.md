---
title: Migration von Elopage
order: 2
excerpt: Von Elopage zu Nexus wechseln und dabei Kunden und Abos behalten
---

# Migration von Elopage

Elopage war lange eine beliebte Plattform für digitale Produkte. Aber steigende Gebühren und eingeschränkte Kontrolle bringen viele zum Umdenken. Nexus bietet dir volle Kontrolle bei 0% Transaktionsgebühren. So gelingt der Umstieg.

## Warum wechseln?

| | Elopage | Nexus |
|---|---------|-------|
| Monatliche Kosten | ab 69 Euro | ab 99 Euro |
| Transaktionsgebühren | 3,9% + Stripe | 0% + Stripe |
| Eigene Domain | Eingeschränkt | Vollständig |
| E-Mail Marketing | Extern nötig | Integriert |
| Eigener Server | Nein | Ja (Hetzner DE) |

Bei einem Monatsumsatz von 5.000 Euro sparst du mit Nexus ca. 165 Euro pro Monat an Transaktionsgebühren - trotz der höheren Grundgebühr.

## Schritt 1: Produkte und Preise nachbauen

Erstelle deine Produkte in Nexus so, wie du sie bei Elopage hast:

1. Gehe zu **Produkte > Neues Produkt**
2. Wähle den passenden Typ (PRODUCT für digitale Produkte, SUBSCRIPTION für Abos)
3. Setze die gleichen Preise wie bei Elopage
4. Füge Beschreibung, Bilder und Downloads hinzu

:::info[Hinweis]
Passe die Produktstruktur an, wenn nötig. Du bist nicht an die Elopage-Logik gebunden. Nexus ist flexibler bei Preismodellen und Produktkombinationen.
:::

## Schritt 2: Stripe-Daten importieren

Da Elopage ebenfalls Stripe nutzt, kannst du deine bestehenden Kundendaten direkt importieren:

1. Gehe zu **Einstellungen > Zahlungen > Stripe**
2. Verbinde denselben Stripe-Account, den du bei Elopage verwendet hast
3. Starte den **Stripe Import** mit der **Merge-Strategie**
4. Nexus importiert: Kunden, aktive Abos, Zahlungsmethoden und Rechnungshistorie

:::tip[Tipp]
Die Merge-Strategie ist ideal für den Wechsel von Elopage. Bestehende Abos laufen nahtlos weiter, weil Stripe die Zahlungen direkt verarbeitet - unabhängig von der Plattform.
:::

## Schritt 3: Kunden werden automatisch übernommen

Nach dem Stripe Import sind deine Kunden in Nexus verfügbar:

- Aktive Abos laufen weiter ohne Unterbrechung
- Kunden sehen ihre Käufe im Kundenportal
- Zahlungsmethoden bleiben erhalten (kein erneutes Eingeben nötig)

Prüfe stichprobenartig einige Kundenprofile, um sicherzugehen, dass alles korrekt importiert wurde.

## Schritt 4: E-Mail Templates anpassen

Nexus verschickt automatisch E-Mails bei Käufen, Aboänderungen und mehr. Passe die Templates an deinen Stil an:

1. Gehe zu **Einstellungen > Kommunikation > E-Mail Templates**
2. Bearbeite die wichtigsten Templates: Kaufbestätigung, Abo-Bestätigung, Rechnung
3. Füge dein Logo und deine Farben hinzu
4. Teste jedes Template mit einer Test-E-Mail

## Schritt 5: Domain umziehen

Verbinde deine Domain mit Nexus:

1. Gehe zu **Einstellungen > System > Hosting**
2. Trage deine Domain ein
3. Erstelle einen CNAME-Eintrag bei deinem Domain-Registrar
4. SSL wird automatisch erstellt

:::warning[Wichtig]
Ändere den DNS-Eintrag erst, wenn Nexus komplett eingerichtet und getestet ist. So vermeidest du Ausfallzeiten.
:::

## Schritt 6: Alte Elopage-Links redirecten

Deine Kunden haben möglicherweise alte Links gespeichert. Stelle sicher, dass diese weiterhin funktionieren:

1. Sammle die wichtigsten Elopage-URLs (Produktseiten, Checkout-Links)
2. Erstelle entsprechende Seiten in Nexus unter ähnlichen URLs
3. Richte bei Elopage eine Weiterleitung ein, falls möglich
4. Informiere deine Kunden über die neue Plattform per E-Mail

## Nach der Migration

- Beobachte die ersten Abrechnungszyklen deiner Abos genau
- Prüfe, ob alle automatischen E-Mails korrekt versendet werden
- Kündige deinen Elopage-Account erst nach 1-2 erfolgreichen Abrechnungszyklen
- Aktualisiere Links auf Social Media, in E-Mails und auf externen Seiten
