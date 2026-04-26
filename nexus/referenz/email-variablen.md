---
title: E-Mail Template-Variablen
order: 1
excerpt: Alle verfuegbaren Variablen fuer E-Mail Templates - gruppiert nach Kontext mit Beispielwerten
---

# E-Mail Template-Variablen

In E-Mail Templates kannst du Variablen einsetzen, die beim Versand automatisch durch echte Werte ersetzt werden.

## Syntax

Variablen werden mit **einfachen geschweiften Klammern** und Punkt-Notation geschrieben:

```
{customer.firstName}
{order.number}
{portal.name}
```

:::warning[Wichtig]
In **E-Mail Templates** verwendest du **einfache** Klammern `{variable}`. Im **Automations-System** (Action-Felder, HTTP_REQUEST-Body) sind dagegen **doppelte** Klammern Standard, z.B. `{{userId}}` oder `{{trigger.order.total}}`. Beide Syntaxen sind kontextabhaengig und nicht austauschbar. Siehe [Automationen](../features/automatisierung.md) fuer Variablen im Automations-Kontext.
:::

Im Template-Editor werden verfuegbare Variablen automatisch vorgeschlagen. Du kannst sie per Klick einfuegen.

## Kunde

In jedem Template verfuegbar:

| Variable | Beschreibung | Beispiel |
|---|---|---|
| `{customer.firstName}` | Vorname | Max |
| `{customer.lastName}` | Nachname | Mustermann |
| `{customer.fullName}` | Voller Name | Max Mustermann |
| `{customer.email}` | E-Mail-Adresse | max@beispiel.de |

## Portal

In jedem Template verfuegbar:

| Variable | Beschreibung | Beispiel |
|---|---|---|
| `{portal.name}` | Name deines Portals | Mein Portal |
| `{portal.url}` | URL deines Portals | https://meinportal.de |

## Bestellung

Verfuegbar in Bestellbestaetigungen, Erstattungen und Zahlungs-E-Mails:

| Variable | Beschreibung | Beispiel |
|---|---|---|
| `{order.number}` | Bestellnummer | ORD-2026-001234 |
| `{order.total}` | Gesamtbetrag | 49,00 EUR |
| `{order.subtotal}` | Zwischensumme (netto) | 41,18 EUR |
| `{order.tax}` | MwSt-Betrag | 7,82 EUR |
| `{order.date}` | Bestelldatum | 15.03.2026 |
| `{order.id}` | Bestell-ID (fuer Links) | cmn... |

## Erstattung

Verfuegbar im Template "Erstattung bestaetigt":

| Variable | Beschreibung | Beispiel |
|---|---|---|
| `{refund.amount}` | Erstattungsbetrag | 49,00 EUR |
| `{refund.type}` | Art der Erstattung | full / partial |

## Fehlgeschlagene Zahlung

Verfuegbar in "Zahlung fehlgeschlagen (Admin)" und "Zahlung fehlgeschlagen (Kunde)":

| Variable | Beschreibung | Beispiel |
|---|---|---|
| `{payment.method}` | Zahlungsart | card / sepa_debit |
| `{payment.failureCode}` | Fehlercode von Stripe | card_declined |
| `{payment.failureMessage}` | Fehlerbeschreibung | Your card was declined. |
| `{support.email}` | Support-E-Mail des Portals | support@beispiel.de |

## Rechnung

Verfuegbar in Rechnungs-E-Mails:

| Variable | Beschreibung | Beispiel |
|---|---|---|
| `{invoice.url}` | Link zur Rechnung | https://... |
| `{invoice.number}` | Rechnungsnummer | INV-2026-001 |

## Abonnement

Verfuegbar in Abo-Bestaetigungen, Verlaengerungen und Kuendigungen:

| Variable | Beschreibung | Beispiel |
|---|---|---|
| `{subscription.productName}` | Produktname | Jahres-Mitgliedschaft |
| `{subscription.amount}` | Betrag | 99,00 EUR |
| `{subscription.nextBillingDate}` | Naechste Abrechnung | 15.04.2026 |
| `{subscription.endDate}` | Enddatum (bei Kuendigung) | 15.03.2027 |

## Event

Verfuegbar in Event-Bestaetigungen und Erinnerungen:

| Variable | Beschreibung | Beispiel |
|---|---|---|
| `{event.name}` | Name des Events | Workshop: Content Marketing |
| `{event.date}` | Datum | 20.04.2026 |
| `{event.time}` | Startzeit | 10:00 |
| `{event.location}` | Veranstaltungsort | Online via Zoom |
| `{participant.firstName}` | Vorname des Teilnehmers | Max |
| `{participant.lastName}` | Nachname des Teilnehmers | Mustermann |
| `{ticketCount}` | Anzahl Tickets | 2 |
| `{joinUrl}` | Link zum Beitreten (Online) | https://... |
| `{calendarUrl}` | Kalender-Download | https://... |
| `{manageTicketsUrl}` | Link zur Ticketverwaltung | https://... |

## Circle Community

Verfuegbar in Circle-Integration-E-Mails:

| Variable | Beschreibung | Beispiel |
|---|---|---|
| `{circle.communityName}` | Community-Name | Premium Community |
| `{circle.communityUrl}` | Community-URL | https://community.beispiel.de |
| `{circle.signupUrl}` | Registrierungs-Link | https://community.beispiel.de/sign_up |
| `{circle.accessGroups}` | Freigeschaltete Gruppen | Premium Members |

## Hosting

Verfuegbar in Hosting-Benachrichtigungen:

| Variable | Beschreibung | Beispiel |
|---|---|---|
| `{hosting.url}` | URL der Instanz | https://app.beispiel.de |
| `{hosting.domain}` | Domain | app.beispiel.de |
| `{hosting.status}` | Status | running |

## Bedingte Bloecke

Du kannst Inhalte nur anzeigen wenn eine Variable einen Wert hat:

```
{variable:show}
Dieser Text wird nur angezeigt wenn die Variable gesetzt ist.
{/variable:show}
```

### Beispiel: Online vs. Vor-Ort

```
{isOnlineParticipant:show}
Dein Zoom-Link: {joinUrl}
Bitte logge dich 5 Minuten vor Beginn ein.
{/isOnlineParticipant:show}

{isOnsiteParticipant:show}
Adresse: Musterstrasse 1, 12345 Berlin
Bitte sei 15 Minuten vor Beginn da.
{/isOnsiteParticipant:show}
```

:::tip[Tipp]
Im Template-Editor siehst du alle verfuegbaren Variablen fuer das jeweilige Template. In der Vorschau werden Beispielwerte eingesetzt, damit du das Layout pruefen kannst.
:::
