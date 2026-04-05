---
title: Webhooks
order: 4
excerpt: Events empfangen und auf Änderungen in Nexus reagieren
---

# Webhooks

Mit Webhooks benachrichtigt Nexus dein System automatisch, wenn etwas passiert - z.B. wenn eine Bestellung bezahlt wird oder ein neuer Kunde sich registriert.

## Webhook einrichten

Gehe zu **Einstellungen > Integrationen > Webhooks** und erstelle einen neuen Webhook:

1. **URL eingeben:** Die HTTPS-URL deines Endpoints (z.B. `https://dein-server.com/webhooks/nexus`)
2. **Events auswählen:** Welche Events sollen gesendet werden?
3. **Signing Key generieren:** Damit kannst du die Echtheit der Payloads verifizieren

:::tip[Tipp]
Verwende immer HTTPS für deine Webhook-URL. Nexus sendet sensible Daten wie Bestelldetails und Kundendaten.
:::

## Verfügbare Events

### Bestellungen

| Event | Beschreibung |
|---|---|
| `order.created` | Neue Bestellung angelegt |
| `order.paid` | Bestellung wurde bezahlt |
| `order.failed` | Zahlung fehlgeschlagen |
| `order.refunded` | Bestellung wurde erstattet |

### Zahlungen

| Event | Beschreibung |
|---|---|
| `payment.completed` | Zahlung erfolgreich abgeschlossen |
| `payment.failed` | Zahlung fehlgeschlagen |

### Kunden

| Event | Beschreibung |
|---|---|
| `customer.created` | Neuer Kunde angelegt |
| `customer.updated` | Kundendaten aktualisiert |

### Abonnements

| Event | Beschreibung |
|---|---|
| `subscription.created` | Neues Abonnement gestartet |
| `subscription.canceled` | Abonnement gekündigt |
| `subscription.renewed` | Abonnement verlängert |

### Formulare

| Event | Beschreibung |
|---|---|
| `form.submitted` | Formular wurde abgesendet |

### Events (Veranstaltungen)

| Event | Beschreibung |
|---|---|
| `event.registered` | Teilnehmer hat sich angemeldet |
| `event.canceled` | Anmeldung wurde storniert |

## Payload-Format

Jeder Webhook liefert einen JSON-Body mit einheitlicher Struktur:

```json
{
  "event": "order.paid",
  "data": {
    "orderId": "ord_abc123",
    "customerId": "cus_def456",
    "total": 9900,
    "currency": "EUR"
  },
  "timestamp": "2026-04-05T12:00:00.000Z",
  "signature": "sha256=abc123..."
}
```

:::info[Hinweis]
Geldbeträge werden immer in der kleinsten Währungseinheit angegeben. `9900` bedeutet 99,00 EUR.
:::

## Signatur verifizieren

Nexus signiert jeden Webhook mit HMAC-SHA256. Die Signatur wird im Header `x-nexus-signature` mitgesendet. Verifiziere sie immer, um sicherzustellen, dass der Webhook wirklich von Nexus kommt.

### Node.js

```javascript
const crypto = require('crypto');

function verifyWebhook(payload, signature, secret) {
  const expected = crypto
    .createHmac('sha256', secret)
    .update(payload)
    .digest('hex');

  return crypto.timingSafeEqual(
    Buffer.from(signature),
    Buffer.from(`sha256=${expected}`)
  );
}

// Express Middleware
app.post('/webhooks/nexus', express.raw({ type: 'application/json' }), (req, res) => {
  const signature = req.headers['x-nexus-signature'];
  const isValid = verifyWebhook(req.body, signature, process.env.WEBHOOK_SECRET);

  if (!isValid) {
    return res.status(401).send('Invalid signature');
  }

  const event = JSON.parse(req.body);
  console.log('Event empfangen:', event.event);

  // Event verarbeiten
  res.status(200).send('OK');
});
```

### Python

```python
import hmac
import hashlib

def verify_webhook(payload: bytes, signature: str, secret: str) -> bool:
    expected = hmac.new(
        secret.encode(),
        payload,
        hashlib.sha256
    ).hexdigest()

    return hmac.compare_digest(signature, f"sha256={expected}")

# Flask Beispiel
@app.route('/webhooks/nexus', methods=['POST'])
def handle_webhook():
    signature = request.headers.get('x-nexus-signature')
    is_valid = verify_webhook(request.data, signature, WEBHOOK_SECRET)

    if not is_valid:
        return 'Invalid signature', 401

    event = request.get_json()
    print(f"Event empfangen: {event['event']}")

    # Event verarbeiten
    return 'OK', 200
```

:::warning[Wichtig]
Verwende immer `timingSafeEqual` (Node.js) bzw. `compare_digest` (Python) zum Vergleich der Signatur. Einfache String-Vergleiche sind anfällig für Timing-Attacken.
:::

## Retry-Logik

Wenn dein Endpoint nicht mit einem 2xx-Statuscode antwortet, versucht Nexus es erneut:

| Versuch | Wartezeit |
|---|---|
| 1. Retry | 1 Minute |
| 2. Retry | 5 Minuten |
| 3. Retry | 30 Minuten |

Nach 3 fehlgeschlagenen Versuchen wird der Webhook als fehlgeschlagen markiert.

:::tip[Tipp]
Antworte so schnell wie möglich mit `200 OK` und verarbeite den Webhook asynchron. Langsame Responses können als Fehler gewertet werden.
:::

## Webhook Logs

Unter **Einstellungen > Logs > Webhook Log** findest du eine Übersicht aller gesendeten Webhooks. Dort siehst du:

- Welches Event gesendet wurde
- HTTP-Statuscode der Antwort
- Zeitpunkt und Dauer
- Ob Retries stattgefunden haben

Das ist besonders nützlich zum Debuggen, wenn Webhooks nicht ankommen oder Fehler auftreten.
