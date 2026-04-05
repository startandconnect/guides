---
title: Automatisierung
order: 4
excerpt: Delivery Actions, E-Mail Templates und automatische Abläufe
---

# Automatisierung

Delivery Actions sind das Herzstück der Automatisierung in Nexus. Du definierst pro Produkt, was bei Kauf, Kündigung oder Rückerstattung passiert. Nexus führt die Actions der Reihe nach aus - zuverlässig und nachvollziehbar.

## Trigger

Jede Delivery Action wird durch ein Event ausgelöst:

- **Bei Kauf** - Sofort nach erfolgreicher Zahlung
- **Bei Kündigung** - Wenn ein Abo gekündigt wird
- **Bei Rückerstattung** - Wenn eine Bestellung erstattet wird

Pro Trigger kannst du beliebig viele Actions hintereinander schalten.

## Action-Typen

| Action | Beschreibung |
|--------|-------------|
| **E-Mail senden** | Automatische E-Mail an den Kunden über ein Template |
| **Webhook** | HTTP POST an eine externe URL mit Bestell- und Kundendaten |
| **Wait** | Pause bis zu einem Zeitpunkt oder bis das Abo abläuft |
| **Provision Instance** | Hosting-Instanz automatisch erstellen (für Hosting-Produkte) |
| **Deprovision Instance** | Hosting-Instanz bei Kündigung automatisch entfernen |

### Beispiel: SaaS-Produkt mit Trial

Ein typischer Ablauf für ein Hosting-Produkt mit Testphase:

1. **Bei Kauf:** E-Mail "Willkommen" senden
2. **Bei Kauf:** Provision Instance (Instanz wird erstellt)
3. **Bei Kauf:** Wait - 3 Tage
4. **Bei Kauf:** E-Mail "Erste Schritte" senden
5. **Bei Kündigung:** E-Mail "Schade, dass du gehst" senden
6. **Bei Kündigung:** Wait - bis Abo abläuft
7. **Bei Kündigung:** Deprovision Instance

Die Reihenfolge der Actions änderst du per **Drag-and-Drop** in der Produktübersicht.

## E-Mail Templates

Unter **E-Mails** erstellst und verwaltest du Templates. Der visuelle Editor bietet:

- Drag-and-Drop Blöcke für Text, Bilder, Buttons und Spalten
- Live-Vorschau und Test-Versand
- Mehrere Templates pro Produkt

### Handlebars-Variablen

In jedem Template stehen dir Variablen zur Verfügung:

```handlebars
Hallo {{vorname}},

danke für deine Bestellung #{{bestellnummer}}.
Dein Zugang: {{portal_url}}
```

Verfügbare Variablen: `vorname`, `nachname`, `email`, `portal_url`, `bestellnummer`, `betrag`, `produktname`, `firmenname` und weitere.

### Konditionale Blöcke

Zeige Inhalte nur an, wenn eine Variable existiert:

```handlebars
{vorname:show}
Hallo {{vorname}},
{/vorname:show}

{vorname:hide}
Hallo,
{/vorname:hide}
```

So passt du E-Mails dynamisch an - z.B. Firmennamen nur anzeigen, wenn einer hinterlegt ist.

:::warning[Wichtig]
Für den E-Mail-Versand brauchst du einen SMTP-Anbieter (z.B. Brevo oder Mailgun). Konfiguriere ihn unter **Einstellungen > E-Mail**, bevor du Delivery Actions mit E-Mails einrichtest.
:::

## Retry-Logik

Falls eine Action fehlschlägt (z.B. Webhook-Timeout oder SMTP-Fehler), versucht Nexus es automatisch erneut. Den Status jeder einzelnen Action siehst du in den Bestelldetails unter **Delivery-Status**.
