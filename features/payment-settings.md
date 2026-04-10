---
title: Zahlungseinstellungen
order: 3
excerpt: Stripe-Integration und Zahlungsoptionen konfigurieren
---

# Zahlungseinstellungen

Unter **Einstellungen** > **Zahlung** > **Stripe** konfigurierst du deine Stripe-Anbindung, Webhook-Verbindung und Benachrichtigungen bei Zahlungsproblemen.

## Stripe verbinden

1. Trage deine **Stripe API Keys** ein (Public Key und Secret Key)
2. Klicke auf **Verbindung pruefen** um die Anbindung zu testen
3. Nexus zeigt dir Account-Name, Modus (Test/Live) und Steuereinstellungen an

:::info[Test vs. Live]
Im Testmodus werden keine echten Zahlungen verarbeitet. Wechsle erst auf Live wenn alles funktioniert.
:::

## Webhook einrichten

Nexus empfaengt Zahlungsereignisse von Stripe ueber einen Webhook. Der Webhook wird automatisch angelegt wenn du auf **Webhook erstellen** klickst.

Wenn der Webhook bereits existiert, aktualisiert Nexus die abonnierten Events automatisch.

## Fehlgeschlagene Zahlungen

Nexus kann dich und/oder deine Kunden automatisch benachrichtigen wenn eine Zahlung fehlschlaegt. Das betrifft zum Beispiel:

- SEPA-Lastschriften die von der Bank zurueckgebucht werden
- Abgelehnte Kreditkarten
- Fehlgeschlagene Zahlungsversuche

### Admin benachrichtigen

Wenn aktiviert, erhaeltst du bei jeder fehlgeschlagenen Zahlung eine E-Mail mit allen Details (Bestellnummer, Kundendaten, Fehlercode, Betrag). Du kannst eine eigene E-Mail-Adresse eintragen oder die Support-E-Mail deines Portals wird verwendet.

### Kunden benachrichtigen

Wenn aktiviert, bekommt der Kunde eine informative E-Mail dass seine Zahlung nicht durchgegangen ist, mit einem Hinweis sich bei dir zu melden.

Beide Benachrichtigungen sind standardmaessig **deaktiviert** und muessen manuell eingeschaltet werden.

Die E-Mail-Inhalte kannst du unter **E-Mails** anpassen (Templates: "Zahlung fehlgeschlagen (Admin)" und "Zahlung fehlgeschlagen (Kunde)").

## Abonnement-Einstellungen

Unter dem Stripe-Block findest du die Abonnement-Einstellungen:

- **Selbstkuendigung erlauben**: Wenn aktiviert, koennen Kunden ihre Abonnements selbst im Kundenportal kuendigen. Wenn deaktiviert, muss die Kuendigung ueber dich als Admin laufen.
