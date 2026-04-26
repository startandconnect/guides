---
title: Status-Referenz
order: 3
excerpt: Alle Status-Werte im System - Bestellungen, Abonnements, Events, Payments, Leads und mehr
---

# Status-Referenz

Nexus verwendet verschiedene Status-Werte um den Zustand von Bestellungen, Abonnements, Events und anderen Objekten abzubilden. Hier findest du alle Status-Werte mit Erklärung, wann sie eintreten.

## Bestellstatus

| Status | Beschreibung | Tritt ein, wenn... |
|---|---|---|
| `PENDING` | Bestellung angelegt, Zahlung ausstehend | Der Kunde den Checkout startet, aber noch nicht bezahlt hat |
| `PAID` | Zahlung erfolgreich eingegangen | Stripe die Zahlung bestätigt (Webhook `payment_intent.succeeded`) |
| `FAILED` | Zahlung fehlgeschlagen | Die Kreditkarte abgelehnt wird oder die Zahlung aus anderem Grund scheitert |
| `REFUNDED` | Vollständig erstattet | Du die komplette Bestellung über Stripe erstattst |
| `CANCELED` | Storniert | Die Bestellung manuell storniert wird (vor Zahlung) |
| `EXPIRED` | Abgelaufen | Die Bestellung nach dem definierten Zeitraum nicht bezahlt wurde |
| `PARTIALLY_REFUNDED` | Teilweise erstattet | Nur ein Teil des Betrags erstattet wurde |

## Abo-Status

| Status | Beschreibung | Tritt ein, wenn... |
|---|---|---|
| `ACTIVE` | Aktives Abonnement | Die Zahlung läuft und das Abo ist gültig |
| `PAST_DUE` | Zahlung überfällig | Eine Abo-Zahlung fehlgeschlagen ist, Stripe aber noch Retries versucht |
| `CANCELED` | Gekündigt | Der Kunde oder du das Abo kündigt |
| `INCOMPLETE` | Unvollständig | Die erste Zahlung beim Abo-Abschluss fehlgeschlagen ist |
| `TRIALING` | In der Testphase | Das Abo mit einer Trial Period gestartet wurde und diese noch läuft |
| `PAUSED` | Pausiert | Das Abo manuell pausiert wurde |

:::info[Hinweis]
Bei `PAST_DUE` versucht Stripe automatisch, die Zahlung erneut einzuziehen (bis zu 4 Versuche). Erst wenn alle Retries scheitern, wechselt der Status zu `CANCELED`.
:::

## Event-Status

| Status | Beschreibung | Tritt ein, wenn... |
|---|---|---|
| `DRAFT` | Entwurf | Das Event erstellt, aber noch nicht veröffentlicht wurde |
| `PUBLISHED` | Veröffentlicht | Das Event zur Registrierung freigegeben wurde |
| `ACTIVE` | Läuft gerade | Das Event aktuell stattfindet (zwischen Start- und Endzeit) |
| `COMPLETED` | Abgeschlossen | Das Event beendet ist (nach der Endzeit) |
| `CANCELED` | Abgesagt | Das Event manuell abgesagt wurde |

## Payment-Status

| Status | Beschreibung | Tritt ein, wenn... |
|---|---|---|
| `PENDING` | Ausstehend | Die Zahlung initiiert, aber noch nicht abgeschlossen ist |
| `COMPLETED` | Abgeschlossen | Die Zahlung erfolgreich verarbeitet wurde |
| `FAILED` | Fehlgeschlagen | Die Zahlung abgelehnt oder nicht verarbeitet werden konnte |
| `REFUNDED` | Erstattet | Die Zahlung vollständig zurückerstattet wurde |

## Lead-Status

Lead-Status sind unter **Einstellungen > Kommunikation > CRM** konfigurierbar. Standard-Werte:

| Status | Beschreibung | Typischer Anwendungsfall |
|---|---|---|
| `LEAD` | Neuer Kontakt | Jemand hat sich für den Newsletter angemeldet oder ein Formular ausgefüllt |
| `SUBSCRIBER` | Abonnent | Hat Newsletter-DOI bestaetigt oder ist in einer Sequence enrolled |
| `PROSPECT` | Interessent | Der Kontakt hat Interesse gezeigt (z.B. Produktseite besucht, Anfrage gestellt) |
| `CUSTOMER` | Kunde | Der Kontakt hat mindestens eine Bestellung abgeschlossen |
| `VIP` | VIP-Kunde | Manuell oder via Automation zugewiesen |
| `INACTIVE` | Inaktiv | Der Kontakt war längere Zeit nicht aktiv oder hat sich abgemeldet |

::: tip[Tipp]
Du kannst eigene Status-Werte hinzufuegen oder bestehende umbenennen. In Automations-Conditions verwendest du den jeweiligen Status-Slug, z.B. `customer.leadStatus equals "VIP"`.
:::

## Nachrichten-Status

| Status | Beschreibung | Tritt ein, wenn... |
|---|---|---|
| `NEW` | Neue Nachricht | Ein Kunde eine Support-Nachricht sendet |
| `IN_PROGRESS` | In Bearbeitung | Ein Teammitglied die Nachricht übernommen hat |
| `RESOLVED` | Gelöst | Das Anliegen bearbeitet und die Lösung kommuniziert wurde |
| `CLOSED` | Geschlossen | Die Konversation endgültig abgeschlossen wurde |

## Produkt-Status

| Status | Beschreibung | Tritt ein, wenn... |
|---|---|---|
| `ACTIVE` | Aktiv | Das Produkt veröffentlicht und kaufbar ist |
| `DRAFT` | Entwurf | Das Produkt erstellt, aber noch nicht veröffentlicht wurde |
| `ARCHIVED` | Archiviert | Das Produkt nicht mehr verkauft wird, aber noch in Bestellhistorien erscheint |

:::tip[Tipp]
Archivierte Produkte werden im Shop nicht mehr angezeigt, bestehende Bestellungen und Abonnements bleiben aber davon unberührt.
:::
