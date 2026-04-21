---
title: Idempotenz
order: 7
excerpt: Ein Request zweimal senden = gleicher Zustand
---

# Idempotenz

Eigenschaft dass ein Request beliebig oft wiederholt werden kann und das System danach im gleichen Zustand ist. Entscheidend fuer verteilte Systeme und Webhooks.

## Beispiel

Stripe sendet dir den Webhook `charge.succeeded`. Dein Server nimmt die Order als bezahlt an und versendet Bestaetigungs-Email.

Netzwerk-Problem, Stripe versucht's nochmal. Selber Webhook kommt an.

**Idempotent implementiert:** Order war schon als bezahlt markiert, Server ignoriert den doppelten Call, keine zweite Email.

**Nicht idempotent:** Server legt eine zweite Zahlung an, Email geht zum zweiten Mal raus, Buchhaltung hat jetzt Doppelbuchung.

## Wie implementieren

- **Event-ID pruefen** - Webhooks haben eindeutige IDs. "Habe ich die schon verarbeitet? Wenn ja, skip."
- **State-Check** - "Ist Order schon `paid`? Dann nicht nochmal als `paid` markieren."
- **Idempotency-Keys** - Client schickt UUID mit, Server cached Resultat gegen UUID

## HTTP-Methoden und Idempotenz

- **GET** - sollte immer idempotent sein (keine Side-Effects)
- **PUT** - idempotent (Set-Value ist idempotent)
- **DELETE** - idempotent (nicht existent oder geloescht = selber Zustand)
- **POST** - typisch NICHT idempotent (laegt neu an). Stripe bietet Idempotency-Key-Header.

## Warum das kritisch ist

In verteilten Systemen gibt's keine Garantie dass ein Request nur einmal ankommt. Netzwerk-Timeouts, Client-Retries, Server-Crashes - alles fuehrt zu Duplikaten.

Idempotente Handler machen Fehler-Recovery trivial: einfach wiederholen.

## Nexus-Beispiele

- Webhook-Handler pruefen Stripe-Event-IDs gegen die Datenbank
- Order-DELETE ist idempotent (404 vs 204 werden beide akzeptiert)
- Login-Token-Validierung ist idempotent (mehrfache Nutzung moeglich bis Ablauf)
- Email-Verify-Token seit v1.3.53 idempotent (Reload der Success-Page bricht nichts mehr)
