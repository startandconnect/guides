---
title: Technik und API
order: 3
excerpt: Schnittstellen, Protokolle und Integrationen
---

# Technik und API

## API (Application Programming Interface)

Definierter Satz von Endpunkten, ueber den Programme miteinander kommunizieren. Nexus hat ueber 1000 dokumentierte API-Endpoints, erreichbar unter `https://deine-domain.de/api/docs`.

Jede Admin-Aktion in der Nexus-UI ist auch per API moeglich.

## REST API

Architektur-Stil fuer APIs, basierend auf HTTP-Methoden (GET, POST, PATCH, DELETE) und Ressourcen (`/api/products`, `/api/orders`). Nexus nutzt REST.

Beispiel: `GET /api/products` listet alle Produkte, `POST /api/products` legt ein neues an.

## Webhook

Event-getriebene Benachrichtigung zwischen Systemen. Statt dass dein System staendig nachfragt ("Hat sich was geaendert?"), ruft das Quell-System dich aktiv an wenn etwas passiert.

In Nexus: Stripe-Webhooks melden Zahlungen, Buchungen, Refunds. Dein eigenes Tool kann Nexus-Webhooks abonnieren um auf Events wie `order.paid` zu reagieren.

## OAuth 2.0

Standardisierter Authentifizierungs-Fluss, bei dem sich Nutzer ueber einen Drittanbieter einloggen (z.B. Google, Circle) statt Passwort einzugeben. Nexus unterstuetzt OAuth 2.0 fuer Community-Integrationen und Custom-SSO.

## MCP (Model Context Protocol)

Offenes Protokoll von Anthropic, ueber das KI-Modelle (Claude, GPT, etc.) strukturiert mit externen Tools reden. Nexus ist MCP-ready: du kannst ueber Claude Code direkt Nexus-API-Calls ausfuehren, Produkte anlegen, Kunden suchen, Newsletter versenden.

**Warum wichtig:** KI-Agenten koennen Nexus wie einen menschlichen Admin bedienen. Automation ohne Zwischen-Klebeband.

## JWT (JSON Web Token)

Kompakter Auth-Token, der Userinformation kryptografisch signiert enthaelt. Nexus nutzt JWT fuer Session-Management.

## SSE (Server-Sent Events)

HTTP-basierte Push-Technologie, bei der der Server kontinuierlich Updates an den Client sendet. Nexus nutzt SSE fuer Live-Updates im Admin-Dashboard (neue Bestellung, Newsletter-Status, etc.).

## Idempotenz

Eigenschaft, dass ein API-Call beliebig oft wiederholt werden kann ohne unterschiedliche Ergebnisse. Wichtig fuer Webhooks: wenn Stripe denselben `charge.succeeded`-Event zweimal sendet, sollte Nexus die Order nur einmal als bezahlt markieren.

## Rate Limiting

Begrenzung der Anzahl API-Requests pro Zeiteinheit. Verhindert Missbrauch und Ueberlast. Nexus hat sanfte Rate-Limits pro API-Key.

## CORS (Cross-Origin Resource Sharing)

Browser-Sicherheits-Mechanismus, der API-Calls von anderen Domains nur mit expliziter Erlaubnis zulaesst. Nexus erlaubt CORS fuer deine Portal-Domain automatisch.

## Cookie / Session-Cookie

Kleiner Datensatz, den der Browser pro Website speichert. Nexus nutzt HttpOnly-Cookies fuer Auth-Tokens (kann von JavaScript nicht gelesen werden - schuetzt vor XSS).

## CSRF (Cross-Site Request Forgery)

Angriff, bei dem eine boesartige Website im Namen des eingeloggten Nutzers Requests an einen Dienst stellt. Nexus schuetzt mit SameSite-Cookies und CSRF-Tokens.
