---
title: SSE
order: 8
excerpt: Server schiebt Events live an den Browser
---

# SSE (Server-Sent Events)

HTTP-basierte Technik bei der der Server kontinuierlich Updates an den Client sendet. Anders als WebSockets nur Server-zu-Client (kein Client-zu-Server).

## Wie das funktioniert

1. Browser oeffnet einen normalen HTTP GET an `/api/stream`
2. Server laesst die Verbindung offen statt sie nach der Antwort zu schliessen
3. Server schreibt bei jedem Event eine kleine Message in den offenen Stream
4. Browser empfaengt per `EventSource`-API die Events live

## Nexus nutzt SSE fuer

- **Live-Updates im Admin**: neue Bestellung erscheint in der Liste ohne Reload
- **Newsletter-Status**: Versand-Progress live
- **Import-Progress**: Stripe-Import zeigt "X von Y importiert" in Echtzeit
- **Scope-Matrix**: Aenderungen an Rollen greifen sofort in anderen Tabs

## Warum nicht WebSockets

- SSE nutzt normales HTTP → kein spezielles Serverless-Setup noetig
- Client ist simpler (nur EventSource-API)
- Firewall-freundlich
- Reconnect-Logic ist im Browser eingebaut

WebSockets sind besser wenn Client oft an Server zurueckschickt (Chat-Anwendungen). Fuer reine Server-Push: SSE ist einfacher.

## Einschraenkungen

- Nur **Server-zu-Client**. Kein bidirektionaler Stream.
- Nur **Text**, keine binaere Daten
- **Connection-Limit** pro Domain (typisch 6) - Browser erlaubt nicht unbegrenzt viele parallele SSE-Verbindungen

## Fallback

Vor EventSource: long-polling. Immer noch im Einsatz wo SSE nicht geht. Langsamer, mehr Overhead, aber universell.

## Konkret in Nexus

`apps/api/src/services/sse/EventBus.ts` + `publishLogAppended()`-Pattern. Ueber 14 Publisher im Code, 8 Admin-Log-Sections + 5 Listen-Pages + Order- und Subscription-Detail konsumieren SSE-Streams.
