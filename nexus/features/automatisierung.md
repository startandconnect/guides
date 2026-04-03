---
title: Automatisierung
order: 4
excerpt: Was nach Kauf, Kündigung oder Storno passiert
---

# Automatisierung

Delivery Actions steuern was automatisch passiert wenn ein Kunde kauft, kündigt oder storniert. Du definierst die Abläufe einmal, Nexus führt sie zuverlässig aus.

## Delivery Actions

Jedes Produkt kann eigene Delivery Actions haben. Diese werden der Reihe nach ausgeführt:

| Action | Beschreibung |
|--------|-------------|
| E-Mail senden | Automatische E-Mail an den Kunden |
| Webhook | HTTP-Request an eine externe URL |
| Warten | Pause (Tage, Stunden oder bis Abo-Ende) |
| Instanz bereitstellen | Hosting-Instanz automatisch erstellen |

## Ablauf konfigurieren

1. Gehe zum Produkt > **Delivery Actions**
2. Füge Actions in der gewünschten Reihenfolge hinzu
3. Pro Action: Typ wählen, konfigurieren, aktivieren

Beispiel-Ablauf nach Kauf:
1. Willkommens-E-Mail senden
2. 3 Tage warten
3. Follow-Up E-Mail mit Tipps senden
4. Webhook an externes System

## Trigger

Actions werden bei verschiedenen Events ausgelöst:

- **Nach Kauf** - Sofort nach erfolgreicher Zahlung
- **Nach Kündigung** - Wenn ein Abo gekündigt wird
- **Nach Storno** - Wenn eine Bestellung storniert wird

## E-Mail Templates

Unter **E-Mails** erstellst du Templates für automatische E-Mails:

- Visueller Editor für das Design
- Variablen für personalisierte Inhalte: `{{vorname}}`, `{{produktname}}`, `{{bestellnummer}}`
- Vorschau und Test-Versand
- Mehrere Templates pro Produkt möglich

:::info[SMTP einrichten]
Für den E-Mail-Versand brauchst du einen SMTP-Anbieter (z.B. Brevo oder Mailgun). Konfiguriere ihn unter **Einstellungen > E-Mail**.
:::

## Retry-Logik

Falls eine Action fehlschlägt (z.B. Webhook-Timeout), versucht Nexus es automatisch erneut. Du siehst den Status jeder Action in der Bestellübersicht.
