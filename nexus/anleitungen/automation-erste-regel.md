---
title: Erste Automation einrichten
order: 6
excerpt: Schritt fuer Schritt eine Rule bauen, die VIP-Status setzt, wenn eine Bestellung ueber 200 EUR liegt
---

# Erste Automation einrichten

Diese Anleitung fuehrt dich durch das Anlegen deiner ersten Rule. Ziel: bei jeder bezahlten Bestellung ueber 200 EUR wird der Kunde automatisch mit dem VIP-Tag markiert und du bekommst eine interne Benachrichtigung.

Du brauchst dafuer ungefaehr 5 Minuten und keinerlei Code-Kenntnisse.

## Schritt 1: Automations oeffnen

1. Klicke in der linken Sidebar auf **Automations** (oben, mit Blitz-Icon)
2. Du landest auf der Discovery-Karte mit den Bereichen Rules, Sequences, Monitor, Templates
3. Klicke auf **Rules**

Falls du den Eintrag nicht siehst: deine Rolle hat moeglicherweise keinen Zugriff auf Automations. Frage einen Admin oder Owner deines Portals.

## Schritt 2: Neue Rule anlegen

1. Klicke oben rechts auf **Neue Rule**
2. Vergib einen Namen, z.B. **VIP-Tag bei Bestellung ueber 200 EUR**
3. Optional: Beschreibung eintragen, z.B. _Setzt VIP-Tag und benachrichtigt das Team_
4. Klicke auf **Anlegen**

Du landest im Editor mit zwei Tabs: **Visual Builder** und **JSON**. Bleib im Visual Builder, das ist die einfachste Variante.

## Schritt 3: Trigger waehlen

1. Im Block **Trigger** klicke auf das Dropdown
2. Suche nach `ORDER_PAID`
3. Waehle den Eintrag **Bestellung bezahlt**

Erwartetes Ergebnis: rechts erscheint eine Vorschau mit den Variablen, die dieser Trigger bereitstellt (`trigger.order.id`, `trigger.order.total`, `trigger.userId`, etc.).

## Schritt 4: Condition hinzufuegen

Wir wollen die Action nur ausloesen, wenn der Bestellwert ueber 200 EUR liegt.

1. Klicke unter dem Trigger auf **Bedingung hinzufuegen**
2. Feld auswaehlen: `trigger.order.total`
3. Operator waehlen: `gte` (groesser oder gleich)
4. Wert eintragen: `20000`

::: warning[Wichtig]
Betraege werden in der kleinsten Waehrungseinheit angegeben. 200 EUR = 20000 Cent. Das gilt ueberall in Nexus, auch in Webhooks und in Email-Variablen.
:::

5. Logik bleibt auf **AND** (Standard, weil wir nur eine Bedingung haben)

## Schritt 5: Erste Action - Tag setzen

1. Im Block **Actions** klicke auf **Action hinzufuegen**
2. Aus der Liste waehle **ADD_TAG**
3. Im Feld **Tag** trage `vip` ein

Wenn der Tag `vip` noch nicht in deinem System existiert, wird er bei der ersten Ausfuehrung automatisch angelegt.

## Schritt 6: Zweite Action - Team benachrichtigen

1. Klicke wieder auf **Action hinzufuegen**
2. Waehle **SEND_INTERNAL_NOTIFICATION**
3. Im Feld **Titel** trage ein: `Neuer VIP-Kunde`
4. Im Feld **Nachricht** trage ein: `Bestellung {{trigger.order.id}} ueber {{trigger.order.total}} Cent. Kunde: {{customer.email}}`

Die `{{...}}`-Platzhalter werden zur Laufzeit mit den echten Werten ersetzt. Du erkennst sie im Visual Builder am Lila-Highlight und kannst sie per Klick aus den verfuegbaren Variablen einfuegen.

## Schritt 7: Speichern

1. Klicke oben rechts auf **Speichern**
2. Erwartetes Ergebnis: gruener Toast **Rule gespeichert**, der Editor bleibt geoeffnet

Die Rule ist gespeichert, aber noch **deaktiviert** (Standard fuer neue Rules). Das ist Absicht - wir wollen erst testen.

## Schritt 8: Mit Test-Run pruefen

1. Klicke oben auf **Test ausfuehren**
2. Modus waehlen: **Single**
3. **Kontakt** auswaehlen: ein Test-Kontakt aus deiner Liste
4. **Trigger-Payload** wird automatisch mit Beispielwerten gefuellt. Stelle sicher, dass `order.total` ueber 20000 liegt
5. Klicke auf **Ausfuehren**

Erwartetes Ergebnis:

- Der Test-Kontakt hat jetzt das Tag `vip` (siehe Kontakt-Detail unter **Kunden**)
- Du selbst hast eine interne Benachrichtigung im Glocken-Icon oben rechts
- Im Tab **Executions** der Rule siehst du einen neuen Eintrag mit Status SUCCESS und Action-Details

Wenn etwas schief lief: der Eintrag steht auf FAILED mit einer Fehlermeldung wie "Tag nicht gefunden" oder "Variable {{...}} nicht aufloesbar". Dann zurueck in den Editor und korrigieren.

## Schritt 9: Rule aktivieren

1. Im Editor oben rechts den Toggle **Aktiv** umlegen
2. Speichern
3. Erwartetes Ergebnis: Rule erscheint in der Rules-Liste mit gruenem Status-Punkt

Ab jetzt laeuft die Rule live bei jeder neuen bezahlten Bestellung.

## Schritt 10: Im Monitor beobachten

Nach den ersten echten Ausloesern:

1. Gehe zu **Automations > Monitor**
2. Du siehst die Rule in der Top-Liste mit Anzahl der Ausfuehrungen der letzten 24h
3. Klicke auf die Rule, um Details zu sehen: erfolgreiche Ausfuehrungen, Fehler, durchschnittliche Laufzeit

Wenn du eine spezifische Bestellung debuggen willst: gehe direkt in die Rule, oeffne den Tab **Executions**, filtere nach Datum oder Kontakt-ID.

## Was als naechstes

- Eine zweite Rule, die auf `TAG_ADDED` mit Tag `vip` reagiert und einen Coupon ausstellt. Dadurch entsteht eine Cascade.
- Eine Sequence "VIP Onboarding" mit drei Mails ueber 14 Tage, die du via `ENROLL_IN_SEQUENCE` startest.
- Eine externe Webhook-Benachrichtigung an Slack via `HTTP_REQUEST` mit hinterlegtem [Credential](../features/credentials.md).

## Verwandte Themen

- [Automationen: Uebersicht aller Trigger und Actions](../features/automatisierung.md)
- [Credentials fuer externe Integrationen](../features/credentials.md)
- [Status-Referenz: Lead-Status und Bestellstatus](../referenz/status-referenz.md)
