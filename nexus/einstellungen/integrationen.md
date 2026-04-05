---
title: Integrationen & API
order: 8
excerpt: API Keys, Webhooks und Storage konfigurieren
---

# Integrationen & API

Unter **Einstellungen > Integrationen** verbindest du externe Dienste und konfigurierst die Nexus API.

## API Keys

Erstelle API Keys, um externe Anwendungen mit deinem Portal zu verbinden.

### Key erstellen

1. Gehe zu **Einstellungen > Integrationen > API Keys**
2. Klicke auf **Neuer API Key**
3. Vergib einen Namen (z.B. "Mein Shop-Integration")
4. Wähle Berechtigungen aus
5. Optional: Ablaufdatum setzen

### Berechtigungen

Jeder Key kann granulare Berechtigungen haben:

- `products:read` / `products:write` - Produkte lesen/bearbeiten
- `orders:read` / `orders:write` - Bestellungen lesen/bearbeiten
- `customers:read` / `customers:write` - Kunden lesen/bearbeiten
- `content:read` / `content:write` - Inhalte lesen/bearbeiten
- `settings:read` / `settings:write` - Einstellungen lesen/bearbeiten

:::warning[Wichtig]
Vergib nur die Berechtigungen, die tatsächlich benötigt werden. Ein Key mit `orders:read` reicht aus, wenn die Integration nur Bestelldaten abfragt.
:::

## Webhooks

Webhooks benachrichtigen externe Systeme in Echtzeit, wenn Ereignisse in deinem Portal stattfinden.

### Webhook einrichten

1. Klicke auf **Neuer Webhook**
2. Trage die Endpoint-URL ein (z.B. `https://mein-service.de/webhook`)
3. Wähle die Events aus:
   - `order.created` - Neue Bestellung
   - `order.completed` - Bestellung abgeschlossen
   - `payment.completed` - Zahlung eingegangen
   - `customer.created` - Neuer Kunde registriert
   - `customer.updated` - Kundendaten geändert
   - `form.submitted` - Formular eingereicht
4. Speichern

### Signing Keys

Jeder Webhook erhält einen **Signing Key**. Damit kannst du auf deiner Seite verifizieren, dass der Request tatsächlich von Nexus kommt. Die Signatur wird im Header `X-Nexus-Signature` mitgesendet.

### Retry-Policy

Fehlgeschlagene Webhook-Zustellungen werden automatisch wiederholt:

- **3 Versuche** mit exponentiell steigendem Abstand (1 Min, 5 Min, 30 Min)
- Nach 3 Fehlversuchen wird der Webhook als fehlgeschlagen markiert

### Delivery Logs

Unter jedem Webhook siehst du die **Delivery Logs** mit Status, Response Code und Payload der letzten Zustellungen.

## Storage

Konfiguriere den Dateispeicher für Uploads:

- **Max-Dateigröße** - Maximale Uploadgröße pro Datei (Standard: 10 MB)
- **Erlaubte Dateitypen** - z.B. `jpg, png, pdf, mp4`
- **Speicher-Limit** - Gesamtvolumen für alle Uploads

:::tip[Tipp]
Beschränke erlaubte Dateitypen auf das Nötigste, um Sicherheitsrisiken zu minimieren. Aktiviere z.B. keine ausführbaren Dateien (.exe, .sh).
:::
