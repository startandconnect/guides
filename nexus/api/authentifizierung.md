---
title: Authentifizierung
order: 3
excerpt: API Keys, Berechtigungen und das Sicherheitsmodell der Nexus API
---

# Authentifizierung

Die Nexus API nutzt API Keys zur Authentifizierung. Jeder Request muss sich ausweisen - ohne gültigen Key gibt es keinen Zugriff.

## API Key erstellen

Du findest die Verwaltung unter **Einstellungen > Integrationen > API Keys**. Dort kannst du neue Keys erstellen und bestehende verwalten.

Jeder API Key beginnt mit dem Prefix `nxs_` und ist an den Benutzer gebunden, der ihn erstellt hat.

:::tip[Tipp]
Erstelle für jede Integration einen eigenen API Key. So kannst du einzelne Integrationen jederzeit widerrufen, ohne andere zu beeinflussen.
:::

## Authentifizierung im Request

Du hast zwei Möglichkeiten, den API Key mitzusenden:

**Variante 1: x-api-key Header**

```bash
curl -s \
  -H "x-api-key: nxs_xxx" \
  -H "User-Agent: Mozilla/5.0" \
  https://deine-domain.com/api/products
```

**Variante 2: Authorization Bearer**

```bash
curl -s \
  -H "Authorization: Bearer nxs_xxx" \
  -H "User-Agent: Mozilla/5.0" \
  https://deine-domain.com/api/products
```

:::warning[Wichtig]
Der Header `User-Agent: Mozilla/5.0` ist Pflicht. Ohne diesen Header blockiert Cloudflare den Request mit einem 403-Fehler.
:::

## Berechtigungen (Scopes)

Beim Erstellen eines API Keys legst du granular fest, auf welche Bereiche er zugreifen darf. Verfügbare Scopes:

| Scope | Beschreibung |
|---|---|
| `products:read` | Produkte lesen |
| `products:write` | Produkte erstellen, bearbeiten, löschen |
| `orders:read` | Bestellungen lesen |
| `orders:create` | Bestellungen erstellen |
| `customers:read` | Kunden lesen |
| `customers:write` | Kunden erstellen, bearbeiten, löschen |
| `coupons:read` | Gutscheine lesen |
| `coupons:write` | Gutscheine erstellen, bearbeiten, löschen |
| `invoices:read` | Rechnungen lesen |
| `subscriptions:read` | Abonnements lesen |
| `subscriptions:write` | Abonnements verwalten |
| `settings:read` | Einstellungen lesen |
| `settings:write` | Einstellungen ändern |
| `plugins:read` | Plugins lesen |
| `plugins:write` | Plugins verwalten |
| `delivery:callback` | Delivery Callbacks empfangen |
| `health:read` | Health-Status abfragen |
| `*` | Vollzugriff auf alle Bereiche |

:::info[Hinweis]
Ein Key mit `products:read` kann Produkte abrufen, aber nicht erstellen oder ändern. Achte darauf, nur die Scopes zu vergeben, die tatsächlich benötigt werden.
:::

## 4-Schichten-Sicherheitsmodell

Die API prüft jeden Request in vier Schichten. Alle vier müssen bestanden werden:

### 1. Global Hook

Jeder eingehende Request wird zentral geprüft: Ist ein gültiger API Key vorhanden? Ist der User-Agent gesetzt? Ist der Key nicht abgelaufen oder widerrufen?

### 2. Route-Level Permissions

Hat der API Key die nötigen Scopes für den angeforderten Endpoint? Ein Key mit `products:read` wird bei `POST /api/products` abgelehnt.

### 3. RBAC (Role-Based Access Control)

Welche Rolle hat der Benutzer, der den Key erstellt hat? Ein API Key kann nie mehr Rechte haben als der zugehörige Benutzer. Wenn der Benutzer keine Admin-Rechte hat, hat auch sein Key keinen Admin-Zugriff.

### 4. Plugin-Local Auth

Plugins können zusätzliche Berechtigungsprüfungen implementieren. Ein Forms-Plugin kann z.B. eigene Zugriffsregeln pro Formular definieren.

## JWT Auth (nur Dashboard)

Neben API Keys gibt es die Cookie-basierte JWT-Authentifizierung. Diese wird ausschließlich vom Dashboard verwendet und ist nicht für externe Integrationen gedacht.

- **AccessToken:** Kurzlebig, wird bei jedem Request mitgesendet
- **RefreshToken:** 7 Tage gültig, erneuert den AccessToken automatisch

:::info[Hinweis]
Für API-Integrationen verwendest du immer API Keys. JWT Auth ist nur für das Dashboard relevant und sollte nicht manuell verwendet werden.
:::

## Fehler bei der Authentifizierung

| Status Code | Bedeutung |
|---|---|
| `401 Unauthorized` | Kein API Key oder ungültiger Key |
| `403 Forbidden` | Key gültig, aber fehlende Berechtigung (Scope) |
| `403 Forbidden` | User-Agent Header fehlt (Cloudflare Block) |

Beispiel einer Fehlerantwort:

```json
{
  "error": "Unauthorized",
  "message": "Invalid or missing API key",
  "statusCode": 401
}
```
