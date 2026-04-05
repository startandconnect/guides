---
title: Pagination und Filter
order: 6
excerpt: Listen durchblättern, filtern und sortieren
---

# Pagination, Filtering und Sorting

Die meisten Listen-Endpoints der Nexus API unterstützen Pagination, Filtering und Sorting. Damit kannst du gezielt die Daten abrufen, die du brauchst.

## Pagination

Verwende die Parameter `page` und `limit`, um durch Listen zu blättern:

| Parameter | Standard | Maximum | Beschreibung |
|---|---|---|---|
| `page` | 1 | - | Aktuelle Seite |
| `limit` | 20 | 100 | Einträge pro Seite |

### Beispiel

```bash
curl "https://deine-domain.com/api/orders?page=2&limit=10" \
  -H "x-api-key: nxs_xxx" \
  -H "User-Agent: Mozilla/5.0"
```

### Response-Struktur

Jede paginierte Antwort enthält ein `pagination`-Objekt:

```json
{
  "data": [
    {
      "id": "ord_abc123",
      "status": "PAID",
      "total": 4900,
      "currency": "EUR",
      "createdAt": "2026-04-05T10:30:00.000Z"
    },
    {
      "id": "ord_def456",
      "status": "PAID",
      "total": 12900,
      "currency": "EUR",
      "createdAt": "2026-04-04T14:15:00.000Z"
    }
  ],
  "pagination": {
    "page": 2,
    "limit": 10,
    "total": 42,
    "totalPages": 5
  }
}
```

:::tip[Tipp]
Nutze `totalPages` um zu prüfen, ob weitere Seiten vorhanden sind. Solange `page < totalPages`, gibt es noch mehr Daten.
:::

## Filtering

Je nach Endpoint stehen verschiedene Filter zur Verfügung:

### Bestellungen (`/api/orders`)

| Parameter | Beispiel | Beschreibung |
|---|---|---|
| `status` | `?status=PAID` | Nach Status filtern (PAID, PENDING, FAILED, REFUNDED) |
| `customerId` | `?customerId=cus_abc` | Bestellungen eines bestimmten Kunden |
| `search` | `?search=Max` | Volltextsuche |

```bash
curl "https://deine-domain.com/api/orders?status=PAID&search=Max" \
  -H "x-api-key: nxs_xxx" \
  -H "User-Agent: Mozilla/5.0"
```

### Produkte (`/api/products`)

| Parameter | Beispiel | Beschreibung |
|---|---|---|
| `type` | `?type=PRODUCT` | Nach Typ filtern (PRODUCT, DIGITAL, SERVICE) |
| `status` | `?status=ACTIVE` | Nach Status filtern (ACTIVE, DRAFT, ARCHIVED) |
| `categoryId` | `?categoryId=cat_xxx` | Nach Kategorie filtern |
| `search` | `?search=kurs` | Volltextsuche |

```bash
curl "https://deine-domain.com/api/products?type=DIGITAL&status=ACTIVE" \
  -H "x-api-key: nxs_xxx" \
  -H "User-Agent: Mozilla/5.0"
```

### Content / Posts (`/api/content/posts`)

| Parameter | Beispiel | Beschreibung |
|---|---|---|
| `type` | `?type=BLOG` | Nach Typ filtern (BLOG, PAGE) |
| `status` | `?status=PUBLISHED` | Nach Status filtern (PUBLISHED, DRAFT) |
| `search` | `?search=anleitung` | Volltextsuche |

```bash
curl "https://deine-domain.com/api/content/posts?type=BLOG&status=PUBLISHED" \
  -H "x-api-key: nxs_xxx" \
  -H "User-Agent: Mozilla/5.0"
```

### Kunden (`/api/customers`)

| Parameter | Beispiel | Beschreibung |
|---|---|---|
| `search` | `?search=mustermann` | Suche nach Name oder E-Mail |

```bash
curl "https://deine-domain.com/api/customers?search=mustermann" \
  -H "x-api-key: nxs_xxx" \
  -H "User-Agent: Mozilla/5.0"
```

## Sorting

Verwende `sortBy` und `sortOrder`, um die Ergebnisse zu sortieren:

| Parameter | Werte | Standard |
|---|---|---|
| `sortBy` | `createdAt`, `updatedAt`, `title`, `total` | `createdAt` |
| `sortOrder` | `asc`, `desc` | `desc` |

```bash
curl "https://deine-domain.com/api/orders?sortBy=total&sortOrder=asc" \
  -H "x-api-key: nxs_xxx" \
  -H "User-Agent: Mozilla/5.0"
```

:::info[Hinweis]
Nicht jeder Endpoint unterstützt alle `sortBy`-Felder. Die verfügbaren Felder findest du in der interaktiven API-Dokumentation unter `/api/docs`.
:::

## Alles kombiniert

Du kannst Pagination, Filtering und Sorting beliebig kombinieren:

```bash
curl "https://deine-domain.com/api/orders?page=2&limit=5&status=PAID&sortBy=createdAt&sortOrder=desc" \
  -H "x-api-key: nxs_xxx" \
  -H "User-Agent: Mozilla/5.0"
```

Dieses Beispiel ruft die zweite Seite der bezahlten Bestellungen ab, sortiert nach Erstelldatum (neueste zuerst), mit 5 Einträgen pro Seite.

### Alle Seiten durchlaufen (Bash)

Wenn du alle Einträge einer Liste abrufen willst, kannst du die Seiten in einer Schleife durchlaufen:

```bash
PAGE=1
TOTAL_PAGES=1

while [ $PAGE -le $TOTAL_PAGES ]; do
  RESPONSE=$(curl -s "https://deine-domain.com/api/orders?page=$PAGE&limit=100&status=PAID" \
    -H "x-api-key: nxs_xxx" \
    -H "User-Agent: Mozilla/5.0")

  echo "$RESPONSE" | jq '.data[]'

  TOTAL_PAGES=$(echo "$RESPONSE" | jq '.pagination.totalPages')
  PAGE=$((PAGE + 1))
done
```

:::warning[Wichtig]
Beachte die Rate Limits der API. Wenn du viele Seiten abrufst, baue eine kurze Pause zwischen den Requests ein.
:::
