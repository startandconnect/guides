---
title: Automation
order: 12
excerpt: Sequenzen von Delivery Actions
---

# Automation

Eine zusammenhaengende Sequenz von Delivery-Actions mit bedingter Logik. Wie Zapier oder Make, aber direkt an Nexus-Events angebunden.

## Unterschied zu Delivery-Action

Einzelne [Delivery-Action](/glossar/nexus-plattform/delivery-action) ist ein einzelner Schritt. Automation ist die ganze Sequenz mit Verzweigungen und Wartezeiten.

## Beispiele

**Purchase-Onboarding:**
```
1. PURCHASE → Email "Willkommen"
2. WAIT 24h → Email "Hast du das Produkt gefunden?"
3. IF NOT OPENED → WAIT 7d → Email "Wir helfen gern"
4. WAIT 30d → Email "Bonus fuer Empfehler"
```

**Form-Submit:**
```
1. FORM_SUBMITTED → Tag "Lead-Hoch-Interesse"
2. Email "Dankesnachricht"
3. Slack-Notification an Sales-Team
```

**Event-Reminder:**
```
1. EVENT_BOOKED → Email "Danke fuer Anmeldung"
2. WAIT until 48h vor Event → Email "Bald gehts los"
3. WAIT until 1h vor Event → SMS "Bereit?"
```

## Wo konfigurierbar

- Pro Produkt (Admin → Produkte → Detail → Delivery Actions)
- Pro Form (forms-Plugin → Automations)
- Pro Event (events-Plugin → Automations)

## Unterschied zu externem Zapier

- **Tiefer integriert** - kennt alle Nexus-Entities direkt
- **Ein System** - kein Zwischen-Klebeband
- **Billiger** - in Nexus enthalten, kein extra Abo
- **Datenschutz** - alle Daten bleiben in deiner Instance

## Wenn Zapier trotzdem sinnvoll ist

Wenn du Tools verbindest die Nexus NICHT eingebaut hat (z.B. Google Sheets Logging, spezielle Slack-Channels, komplexe If-This-Then-That). Dann: Nexus sendet Webhook → Zapier → dein Tool.

## Limits

Automation-Chains koennen beliebig lang werden. Aber: je laenger, je schwieriger zu debuggen. Faustregel: max 5-7 Schritte pro Kette. Fuer Komplexes lieber mehrere kurze Ketten.

## Debugging

Pro Order im Admin siehst du die vollstaendige Automation-Execution-Timeline. Welche Schritte haben stattgefunden, wann, mit welchem Ergebnis. Bei Fehler: Retry-Button.
