---
title: Rate Limiting
order: 9
excerpt: Nicht zu viele Requests in zu kurzer Zeit
---

# Rate Limiting

Begrenzung der Anzahl API-Requests die ein Client in einem Zeitraum senden darf. Schutz vor Missbrauch, Ueberlast, Abuse.

## Warum

- **Serverlast** - ein Bot der 10 000 Requests pro Sekunde sendet bringt dein System runter
- **Fairness** - ein einzelner Kunde soll nicht alle Ressourcen verbrauchen
- **Security** - Brute-Force gegen Login, Credential-Stuffing
- **Kosten** - Stripe, OpenAI etc. kosten pro Call. Rate-Limit verhindert Kostenexplosion durch Bugs

## Limits-Strategien

- **Fixed Window** - X Requests pro Stunde. Einfach, aber "bursts" moeglich am Zeitfenster-Rand.
- **Sliding Window** - X Requests in den letzten 60 Sekunden. Fairer.
- **Token Bucket** - jede Sekunde kommt ein Token dazu, jeder Request kostet einen. Erlaubt kurze Bursts.

## HTTP-Response

- **429 Too Many Requests** - du hast das Limit ueberschritten
- Header `Retry-After: 60` - warte 60 Sekunden
- Header `X-RateLimit-Remaining: 0` - keine Requests mehr uebrig

## Wie damit umgehen

Client-seitig:
- Exponential Backoff bei 429 (1s, 2s, 4s, 8s warten)
- Rate-Limit-Response-Header respektieren
- Requests buendeln wo moeglich

## Nexus-Rate-Limits

- **API-Keys** haben sanftes Rate-Limit, typisch kein Problem
- **Login** strengeres Limit (gegen Brute-Force)
- **Public-Endpoints** (Forms-Submit, Newsletter) spezielle Limits pro IP
- **Stripe-Calls** intern: Nexus respektiert Stripe's Rate-Limits automatisch

Im Standardbetrieb trifft ein Kunde nie ein Limit. Wenn doch: Admin-Log zeigt die blockierten Requests.
