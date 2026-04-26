---
title: Automationen
order: 4
excerpt: Regeln und Sequenzen mit 30 Triggern und 23 Actions, Visual Builder und JSON-Editor
---

# Automationen

Automationen sind das Herzstueck der Workflows in Nexus. Du beschreibst, was passieren soll, wenn ein Ereignis eintritt, und Nexus fuehrt es aus, ohne dass du klicken musst. Du erreichst sie ueber den Top-Level-Eintrag **Automations** in der Sidebar.

Es gibt zwei Bausteine:

- **Rules (Regeln)** reagieren auf ein einzelnes Ereignis (z.B. neue Bestellung, Tag wurde gesetzt) und fuehren eine oder mehrere Actions aus. Optional mit Bedingungen.
- **Sequences (Sequenzen)** sind Ketten aus mehreren Schritten mit Wartezeiten dazwischen, z.B. eine 4-teilige Welcome-Mail-Reihe.

Du kannst beides parallel nutzen. Rules sind fuer punktuelle Reaktionen gedacht, Sequences fuer mehrstufige Verlaeufe.

## Wann brauchst du Automationen

Typische Use-Cases:

- Bei jedem neuen Kontakt automatisch Tag setzen und Welcome-Mail senden
- Bei einer Bestellung ueber 200 EUR den Kunden als VIP markieren
- Wenn ein Warenkorb abgebrochen wurde, nach 1 Stunde eine Erinnerung schicken
- Bei Geburtstagen einen Coupon ausstellen
- Wenn ein Formular abgesendet wird, ein Deal in der Pipeline anlegen
- Bei Abo-Kuendigung eine Win-Back-Sequenz starten

## Sidebar-Struktur

Unter **Automations** findest du vier Bereiche:

| Bereich | Inhalt |
|---|---|
| **Rules** | Liste aller Regeln, Editor, Test-Funktion |
| **Sequences** | Multi-Step-Verlaeufe mit Wartezeiten |
| **Monitor** | Live-Sicht auf Ausfuehrungen, Erfolgs- und Fehlerraten der letzten 24h |
| **Templates** | Vorgefertigte Rules und Sequences zum Ein-Klick-Installieren |

Credentials (Auth-Daten fuer HTTP_REQUEST und externe Webhooks) verwaltest du unter **Einstellungen > Automations > Credentials**. Mehr dazu unter [Credentials](./credentials.md).

## Trigger: Was loest eine Rule aus

Triggers sind die Ereignisse, auf die eine Rule reagiert. Es gibt 30 vordefinierte Triggers, gruppiert nach Bereich:

### User-Lifecycle

| Trigger | Wann |
|---|---|
| `NEW_CONTACT` | Kontakt zum ersten Mal angelegt |
| `USER_REGISTERED` | Nutzer registriert sich am Portal |
| `USER_LOGIN` | Login |
| `USER_DELETED` | Konto geloescht |

### Order und Payment

| Trigger | Wann |
|---|---|
| `ORDER_CREATED` | Bestellung wurde angelegt |
| `ORDER_PAID` | Zahlung erfolgreich |
| `ORDER_FAILED` | Zahlung fehlgeschlagen |
| `ORDER_REFUNDED` | Erstattung durchgefuehrt |
| `CART_ABANDONED` | Warenkorb verlassen |

### Subscriptions

| Trigger | Wann |
|---|---|
| `SUBSCRIPTION_STARTED` | Abo gestartet |
| `SUBSCRIPTION_RENEWED` | Verlaengerung erfolgreich |
| `SUBSCRIPTION_CANCELED` | Kuendigung erfolgt |
| `SUBSCRIPTION_TRIAL_ENDING` | Trial laeuft in den naechsten Tagen aus |

### Engagement

| Trigger | Wann |
|---|---|
| `EMAIL_OPENED` | Empfaenger oeffnet Mail |
| `EMAIL_CLICKED` | Empfaenger klickt Link in Mail |
| `FORM_SUBMITTED` | Formular abgesendet |
| `EVENT_REGISTERED` | Anmeldung zu einer Veranstaltung |

### CRM

| Trigger | Wann |
|---|---|
| `TAG_ADDED` | Tag wurde gesetzt |
| `TAG_REMOVED` | Tag wurde entfernt |
| `LEAD_STATUS_CHANGED` | Lead-Status hat sich geaendert |
| `CUSTOM_FIELD_CHANGED` | Custom-Field wurde aktualisiert |
| `DEAL_STAGE_CHANGED` | Deal hat Pipeline-Stufe gewechselt |
| `MESSAGE_RECEIVED` | Neue Support-Nachricht eingegangen |

### Access

| Trigger | Wann |
|---|---|
| `ACCESS_GRANTED` | Nutzer wurde zu einer Access-Group hinzugefuegt |
| `ACCESS_REVOKED` | Zugriff entzogen |

### Time

| Trigger | Wann |
|---|---|
| `BIRTHDAY` | Geburtstag eines Kontakts |
| `INACTIVITY` | Kontakt war seit X Tagen nicht aktiv |
| `SCHEDULED_TIME` | Cron-basierter Zeitpunkt |
| `DATE_FIELD_REACHED` | Datum aus einem Custom-Field erreicht |
| `ANNIVERSARY` | Jahrestag, z.B. Kunde-seit-Datum |

## Actions: Was die Rule tut

Es gibt 23 Actions, gruppiert nach Bereich:

### CRM

- **ADD_TAG** / **REMOVE_TAG**: Tag setzen oder entfernen
- **CHANGE_LEAD_STATUS**: Neuen Lead-Status setzen
- **MARK_VIP** / **ARCHIVE_USER**: Sonderstati setzen
- **SET_CUSTOM_FIELD** / **INCREMENT_CUSTOM_FIELD**: Custom-Field schreiben oder hochzaehlen
- **ADD_NOTE**: Interne Notiz an Kontakt anhaengen

### Kommunikation

- **SEND_EMAIL**: Email-Template an Kontakt senden
- **SEND_INTERNAL_NOTIFICATION**: Push an Team-Mitglieder
- **ENROLL_IN_SEQUENCE** / **UNSUBSCRIBE_FROM_SEQUENCE**: Sequenzen starten oder verlassen
- **ADD_TO_LIST**: Kontakt einem Newsletter-Segment zuweisen

### Commerce

- **GRANT_COUPON**: Einmal-Coupon erstellen und ausgeben
- **CREATE_DEAL**: Deal in der Pipeline anlegen
- **ASSIGN_OWNER**: Verantwortlichen aus dem Team zuweisen

### Tasks und Access

- **CREATE_TASK**: Aufgabe ans Team
- **ADD_TO_ACCESS_GROUP** / **REMOVE_FROM_ACCESS_GROUP**: Zugriffe auf interne Bereiche steuern

### Integration

- **WEBHOOK**: HTTP-POST an externe URL (signed via Setting-Secret)
- **HTTP_REQUEST**: Beliebiger HTTP-Call mit URL, Methode, Headern, Query und Body. Optional mit Credential fuer Auth.

## Conditions: Wann die Action laeuft

Bedingungen filtern, ob eine Rule fuer einen konkreten Vorfall greift. Du kannst beliebig viele Conditions kombinieren mit AND oder OR.

### Operatoren

| Operator | Bedeutung |
|---|---|
| `equals` / `not_equals` | Gleich / ungleich |
| `contains` / `not_contains` | Enthaelt / enthaelt nicht (case-insensitive) |
| `in` / `not_in` | Wert in Liste / nicht in Liste |
| `gt` / `lt` / `gte` / `lte` | Groesser / kleiner als (numerisch) |

### Date-Operatoren

Fuer Felder mit Datumswerten:

| Operator | Bedeutung |
|---|---|
| `before` | Datum liegt vor X |
| `after` | Datum liegt nach X |
| `within_days` | Datum liegt innerhalb der naechsten N Tage |
| `older_than_days` | Datum liegt mehr als N Tage zurueck |

Beispiele:

- `subscription.endDate before 2026-12-31`
- `customer.lastLoginAt older_than_days 30`
- `event.startDate within_days 7`

### AND vs. OR

- **AND** (Standard): alle Bedingungen muessen erfuellt sein
- **OR**: eine Bedingung reicht

Beispiel OR: VIP setzen, wenn Bestellwert ueber 200 EUR ODER Anzahl bisheriger Bestellungen ueber 5.

## Variable-Interpolation

In Action-Feldern (z.B. URLs, Notes, Email-Templates, HTTP-Body) kannst du Werte aus dem ausloesenden Ereignis einsetzen. Syntax: doppelte geschweifte Klammern.

| Platzhalter | Bedeutung |
|---|---|
| `{{userId}}` | ID des betroffenen Kontakts |
| `{{trigger.formTitle}}` | Titel des ausgeloesten Formulars |
| `{{trigger.order.total}}` | Gesamtbetrag der Bestellung |
| `{{trigger.tag}}` | Soeben gesetzter oder entfernter Tag |
| `{{trigger.oldStatus}}` / `{{trigger.newStatus}}` | Vorheriger und neuer Status bei Status-Change |

Verfuegbare Variablen haengen vom Trigger ab. Im Visual Builder werden dir die passenden Variablen pro Trigger vorgeschlagen.

::: warning[Wichtig]
Die doppelten Klammern `{{...}}` gelten in Automations. In normalen Email-Templates kommen einfache Klammern `{customer.firstName}` zum Einsatz. Siehe auch [E-Mail Template-Variablen](../referenz/email-variablen.md).
:::

## Visual Builder vs. JSON-Editor

Jede Rule und Sequence kannst du in zwei Modi bearbeiten:

- **Visual Builder**: klickbare Oberflaeche fuer Trigger, Conditions, Actions. Dropdowns fuer Werte, Auto-Complete fuer Variablen, sofortige Vorschau der Cascade-Wirkung.
- **JSON-Editor**: das gleiche Objekt als JSON. Praktisch wenn du Rules versionieren, exportieren oder mit einer KI generieren lassen willst.

Beide Modi sind synchron. Aenderungen in einem Modus erscheinen sofort im anderen. Welche Felder erlaubt sind, wird durch das Schema (`/api/automations/schema`) vorgegeben.

## Beispiele

### Beispiel 1: Welcome-Mail bei neuem Kontakt

**Trigger**: `NEW_CONTACT`
**Conditions**: keine
**Actions**:
1. `ADD_TAG` mit `tag: "welcome-pending"`
2. `SEND_EMAIL` mit `templateSlug: "welcome"`

### Beispiel 2: VIP bei hohem Bestellwert

**Trigger**: `ORDER_PAID`
**Conditions** (AND): `trigger.order.total gte 20000` (Cent, also 200 EUR)
**Actions**:
1. `MARK_VIP`
2. `ADD_NOTE` mit `note: "VIP wegen Bestellung {{trigger.order.id}} ueber {{trigger.order.total}}"`
3. `GRANT_COUPON` mit Code-Praefix `vip-`

### Beispiel 3: Cart-Abandoned-Recovery

**Trigger**: `CART_ABANDONED`
**Conditions** (AND): `customer.email is not empty`
**Actions**:
1. `ADD_TAG` mit `tag: "cart-abandoned"`
2. `SEND_EMAIL` mit `templateSlug: "cart-recovery"`
3. `ENROLL_IN_SEQUENCE` mit `sequenceSlug: "cart-recovery-3-step"`

### Beispiel 4: Win-Back bei Abo-Kuendigung

**Trigger**: `SUBSCRIPTION_CANCELED`
**Conditions**: keine
**Actions**:
1. `CHANGE_LEAD_STATUS` auf `INACTIVE`
2. `ENROLL_IN_SEQUENCE` mit `sequenceSlug: "win-back"`

### Beispiel 5: Geburtstag mit Coupon

**Trigger**: `BIRTHDAY` (Cron, taeglich)
**Conditions** (AND): `customer.leadStatus equals "CUSTOMER"`
**Actions**:
1. `GRANT_COUPON` mit Wert 10 EUR
2. `SEND_EMAIL` mit Template `birthday`

## Cascading: Rules loesen Rules aus

Wenn eine Rule via Action z.B. `ADD_TAG` ausfuehrt, fired das den `TAG_ADDED`-Trigger. Andere Rules, die darauf hoeren, laufen ebenfalls. So entstehen Ketten:

```
NEW_CONTACT
  -> Rule 1: ADD_TAG "welcome-pending"
    -> TAG_ADDED triggert Rule 2: SEND_EMAIL Welcome
      -> EMAIL_SENT triggert Rule 3: CREATE_TASK "Follow-Up in 7 Tagen"
```

Nexus schuetzt vor Endlos-Schleifen: maximale Chain-Tiefe 5, eine Rule kann sich nicht selbst aufrufen.

## Test und Monitor

### Eine Rule testen

Im Editor auf **Test ausfuehren** klicken. Du waehlst:

- **Single**: gegen einen konkreten Kontakt (Empfehlung fuer User-bezogene Actions wie ADD_TAG)
- **Broadcast**: ohne userId, sinnvoll fuer User-agnostische Actions (Webhook, Internal-Notification)

Das Test-Run ignoriert disabled-Status, fan-out auf andere Rules ist deaktiviert. Du siehst sofort Erfolg oder Fehler mit Details.

### Live-Monitor

Unter **Automations > Monitor** siehst du:

- Letzte 24h: Anzahl Ausfuehrungen, Erfolgs- und Fehlerquote
- Top-Rules nach Volumen
- Top-Fehlerquellen
- Detail-Drill-Down pro Rule mit Pagination

Pro Rule findest du im Editor unter **Executions** eine Liste der letzten Aufrufe inkl. Trigger-Payload, Action-Ergebnis und Chain-Tiefe.

## Templates

Unter **Automations > Templates** findest du fertige Vorlagen:

- Welcome-Mail bei neuem Kontakt
- VIP-Markierung bei hohem Bestellwert
- Cart-Recovery
- Refund-Notify
- Payment-Failed-Notify
- Subscription-Renewed-Tag
- Win-Back bei Kuendigung

Plus 5 fertige Sequences (Welcome-Series, Cart-Recovery, Post-Purchase-Follow-Up, Win-Back, Event-Pre-Reminder).

Mit einem Klick installierst du eine Vorlage. Sie wird **disabled** angelegt, damit du sie pruefen und anpassen kannst, bevor sie scharfgeschaltet wird.

## After-Sales pro Produkt

Unabhaengig vom Automations-System gibt es weiterhin den produktbezogenen **After-Sales**-Bereich. Den findest du unter **Produkt > After-Sales**. Er ist gedacht fuer Aktionen, die direkt zum Lebenszyklus eines konkreten Produkts gehoeren:

- E-Mail nach Kauf, Kuendigung oder Erstattung versenden
- Bei Hosting-Produkten: Instanz provisionieren oder deprovisionieren
- Wartezeiten zwischen Schritten

Wenn du eine Action fuer "alle Produkte" oder fuer einen anderen Trigger als Kauf/Kuendigung/Erstattung brauchst, nutze besser das Automations-System.

::: tip[Tipp]
Faustregel: produktspezifische Auslieferung -> After-Sales am Produkt. Ueber-Produkt-greifende Workflows, CRM-Logik, externe Integrationen -> Automations.
:::

## Verwandte Themen

- [Erste Automation: VIP bei Bestellung ueber 200 EUR](../anleitungen/automation-erste-regel.md)
- [Credentials fuer Webhooks und HTTP-Calls](./credentials.md)
- [E-Mail Template-Variablen](../referenz/email-variablen.md)
- [Webhooks (von Nexus an externe Systeme)](../api/webhooks.md)
