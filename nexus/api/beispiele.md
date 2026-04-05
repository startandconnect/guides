---
title: Praxisbeispiele
order: 5
excerpt: Konkrete Code-Beispiele für häufige API-Aufgaben
---

# Praxisbeispiele

Hier findest du fertige Code-Beispiele für die häufigsten API-Aufgaben. Kopiere sie und passe Domain und API Key an.

:::info[Hinweis]
In allen Beispielen musst du `deine-domain.com` durch deine tatsächliche Nexus-Domain und `nxs_xxx` durch deinen API Key ersetzen.
:::

## Produkte

### Produkt erstellen

```bash
curl -X POST https://deine-domain.com/api/products \
  -H "x-api-key: nxs_xxx" \
  -H "User-Agent: Mozilla/5.0" \
  -H "Content-Type: application/json" \
  -d '{
    "title": "Mein Produkt",
    "type": "PRODUCT",
    "status": "ACTIVE"
  }'
```

Antwort:

```json
{
  "id": "prod_abc123",
  "title": "Mein Produkt",
  "type": "PRODUCT",
  "status": "ACTIVE",
  "createdAt": "2026-04-05T12:00:00.000Z"
}
```

### Alle Produkte abrufen

```bash
curl "https://deine-domain.com/api/products" \
  -H "x-api-key: nxs_xxx" \
  -H "User-Agent: Mozilla/5.0"
```

### Produkt aktualisieren

```bash
curl -X PATCH https://deine-domain.com/api/products/prod_abc123 \
  -H "x-api-key: nxs_xxx" \
  -H "User-Agent: Mozilla/5.0" \
  -H "Content-Type: application/json" \
  -d '{
    "title": "Neuer Produktname",
    "status": "DRAFT"
  }'
```

## Bestellungen

### Alle Bestellungen abrufen

```bash
curl "https://deine-domain.com/api/orders?status=PAID&limit=10" \
  -H "x-api-key: nxs_xxx" \
  -H "User-Agent: Mozilla/5.0"
```

Antwort:

```json
{
  "data": [
    {
      "id": "ord_abc123",
      "status": "PAID",
      "total": 4900,
      "currency": "EUR",
      "customer": {
        "email": "kunde@example.com"
      },
      "createdAt": "2026-04-05T10:30:00.000Z"
    }
  ],
  "pagination": {
    "page": 1,
    "limit": 10,
    "total": 42,
    "totalPages": 5
  }
}
```

### Einzelne Bestellung abrufen

```bash
curl "https://deine-domain.com/api/orders/ord_abc123" \
  -H "x-api-key: nxs_xxx" \
  -H "User-Agent: Mozilla/5.0"
```

## Kunden

### Kunden anlegen

```bash
curl -X POST https://deine-domain.com/api/customers \
  -H "x-api-key: nxs_xxx" \
  -H "User-Agent: Mozilla/5.0" \
  -H "Content-Type: application/json" \
  -d '{
    "email": "kunde@example.com",
    "firstName": "Max",
    "lastName": "Mustermann"
  }'
```

Antwort:

```json
{
  "id": "cus_def456",
  "email": "kunde@example.com",
  "firstName": "Max",
  "lastName": "Mustermann",
  "createdAt": "2026-04-05T12:00:00.000Z"
}
```

### Kunden suchen

```bash
curl "https://deine-domain.com/api/customers?search=mustermann" \
  -H "x-api-key: nxs_xxx" \
  -H "User-Agent: Mozilla/5.0"
```

## Blog / Content

### Blog-Artikel erstellen

```bash
curl -X POST https://deine-domain.com/api/content/posts \
  -H "x-api-key: nxs_xxx" \
  -H "User-Agent: Mozilla/5.0" \
  -H "Content-Type: application/json" \
  -d '{
    "type": "BLOG",
    "title": "Mein Artikel",
    "slug": "mein-artikel",
    "content": "<p>Inhalt des Artikels</p>"
  }'
```

Antwort:

```json
{
  "id": "post_ghi789",
  "type": "BLOG",
  "title": "Mein Artikel",
  "slug": "mein-artikel",
  "status": "DRAFT",
  "createdAt": "2026-04-05T12:00:00.000Z"
}
```

### Alle Blog-Artikel abrufen

```bash
curl "https://deine-domain.com/api/content/posts?type=BLOG" \
  -H "x-api-key: nxs_xxx" \
  -H "User-Agent: Mozilla/5.0"
```

## Formulare (Public API)

Das Forms-Plugin bietet einen öffentlichen Endpoint, der keinen API Key benötigt. Damit kannst du Formulare direkt von deiner Website oder App abschicken.

### Formular absenden

```bash
curl -X POST https://deine-domain.com/api/plugins/forms/public/forms/kontakt/submit \
  -H "Content-Type: application/json" \
  -d '{
    "data": {
      "name": "Max",
      "email": "max@example.com",
      "nachricht": "Hallo!"
    }
  }'
```

:::tip[Tipp]
Ersetze `kontakt` in der URL durch den Slug deines Formulars. Den Slug findest du in den Formular-Einstellungen.
:::

Antwort:

```json
{
  "success": true,
  "submissionId": "sub_xyz789"
}
```

## Gutscheine

### Gutschein erstellen

```bash
curl -X POST https://deine-domain.com/api/coupons \
  -H "x-api-key: nxs_xxx" \
  -H "User-Agent: Mozilla/5.0" \
  -H "Content-Type: application/json" \
  -d '{
    "code": "SOMMER2026",
    "type": "PERCENTAGE",
    "value": 20,
    "maxUses": 100
  }'
```

### Alle Gutscheine abrufen

```bash
curl "https://deine-domain.com/api/coupons" \
  -H "x-api-key: nxs_xxx" \
  -H "User-Agent: Mozilla/5.0"
```

## Health Check

```bash
curl "https://deine-domain.com/api/health" \
  -H "x-api-key: nxs_xxx" \
  -H "User-Agent: Mozilla/5.0"
```

Antwort:

```json
{
  "status": "ok",
  "version": "2.x.x",
  "uptime": 86400
}
```
