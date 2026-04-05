---
title: Automatisierung
order: 4
excerpt: Delivery Actions, E-Mail Templates und automatische Abläufe
---

# Automatisierung

Delivery Actions sind das Herzstück der Automatisierung in Nexus. Du definierst pro Produkt, was bei Kauf, Kündigung oder Rückerstattung passiert. Nexus führt die Actions der Reihe nach aus - zuverlässig und nachvollziehbar.

## Trigger

Jede Delivery Action wird durch ein Event ausgelöst:

- **Bei Kauf** - Sofort nach erfolgreicher Zahlung
- **Bei Kündigung** - Wenn ein Abo gekündigt wird
- **Bei Rückerstattung** - Wenn eine Bestellung erstattet wird

Pro Trigger kannst du beliebig viele Actions hintereinander schalten.

## Action-Typen

| Action | Beschreibung |
|--------|-------------|
| **E-Mail senden** | Automatische E-Mail an den Kunden über ein Template |
| **Webhook** | HTTP POST an eine externe URL mit Bestell- und Kundendaten |
| **Wait** | Pause bis zu einem Zeitpunkt oder bis das Abo abläuft |
| **Provision Instance** | Hosting-Instanz automatisch erstellen (für Hosting-Produkte) |
| **Deprovision Instance** | Hosting-Instanz bei Kündigung automatisch entfernen |

### Beispiel: SaaS-Produkt mit Trial

Ein typischer Ablauf für ein Hosting-Produkt mit Testphase:

1. **Bei Kauf:** E-Mail "Willkommen" senden
2. **Bei Kauf:** Provision Instance (Instanz wird erstellt)
3. **Bei Kauf:** Wait - 3 Tage
4. **Bei Kauf:** E-Mail "Erste Schritte" senden
5. **Bei Kündigung:** E-Mail "Schade, dass du gehst" senden
6. **Bei Kündigung:** Wait - bis Abo abläuft
7. **Bei Kündigung:** Deprovision Instance

Die Reihenfolge der Actions änderst du per **Drag-and-Drop** in der Produktübersicht.

## E-Mail Templates

Unter **E-Mails** erstellst und verwaltest du Templates. Der visuelle Editor bietet:

- Drag-and-Drop Blöcke für Text, Bilder, Buttons und Spalten
- Live-Vorschau und Test-Versand
- Mehrere Templates pro Produkt

### Handlebars-Variablen

In jedem Template stehen dir Variablen zur Verfügung:

```handlebars
Hallo {{vorname}},

danke für deine Bestellung #{{bestellnummer}}.
Dein Zugang: {{portal_url}}
```

Verfügbare Variablen: `vorname`, `nachname`, `email`, `portal_url`, `bestellnummer`, `betrag`, `produktname`, `firmenname` und weitere.

### Konditionale Blöcke

Zeige Inhalte nur an, wenn eine Variable existiert:

```handlebars
{vorname:show}
Hallo {{vorname}},
{/vorname:show}

{vorname:hide}
Hallo,
{/vorname:hide}
```

So passt du E-Mails dynamisch an - z.B. Firmennamen nur anzeigen, wenn einer hinterlegt ist.

:::warning[Wichtig]
Für den E-Mail-Versand brauchst du einen SMTP-Anbieter (z.B. Brevo oder Mailgun). Konfiguriere ihn unter **Einstellungen > E-Mail**, bevor du Delivery Actions mit E-Mails einrichtest.
:::

## Automation erstellen - Schritt für Schritt

So richtest du eine Delivery Action für ein Produkt ein:

1. **Navigiere zu Manage > Produkte** und wähle das gewünschte Produkt aus
2. Wechsle zum Bereich **After-Sales**
3. Klicke auf **Neue Aktion**
4. **Trigger wählen** - entscheide, wann die Action ausgelöst wird:
   - *Bei Kauf* - direkt nach erfolgreicher Zahlung
   - *Bei Kündigung* - wenn der Kunde sein Abo kündigt
   - *Bei Rückerstattung* - wenn du eine Bestellung erstattest
5. **Action-Typ wählen:**
   - *E-Mail senden* - wähle ein bestehendes E-Mail-Template aus. Die verfügbaren Variablen (Vorname, Produktname, etc.) werden automatisch befüllt
   - *Webhook* - gib die Ziel-URL ein und definiere den Payload. Nexus sendet einen HTTP POST mit Bestell- und Kundendaten
   - *Wait* - wähle einen festen Zeitpunkt (z.B. "3 Tage nach Kauf") oder die Option "bis Abo abläuft"
   - *Provision Instance* - für Hosting-Produkte: erstellt automatisch eine Server-Instanz für den Kunden
   - *Deprovision Instance* - für Hosting-Produkte: schaltet die Instanz automatisch ab
6. **Reihenfolge anpassen** - ziehe die Actions per Drag-and-Drop in die gewünschte Reihenfolge. Die Actions werden von oben nach unten abgearbeitet
7. **Speichern** - die Automation ist sofort aktiv

:::info[Hinweis]
Du kannst pro Trigger beliebig viele Actions anlegen. Kombiniere z.B. eine E-Mail, eine Wartezeit und eine zweite E-Mail zu einer automatischen Kette.
:::

## Beispiel: E-Mail-Kette nach Eventkauf

Du verkaufst ein Seminar und möchtest dem Kunden automatisch alle relevanten Infos schicken. So richtest du das ein:

1. **Aktion 1 - Buchungsbestätigung (sofort):** Erstelle eine Action mit Trigger "Bei Kauf" und Typ "E-Mail senden". Wähle ein Template mit Bestellbestätigung und den Event-Details
2. **Aktion 2 - Wait (2 Wochen vor Event):** Füge eine Wait-Action hinzu und setze den Zeitpunkt auf 2 Wochen vor dem Event-Datum
3. **Aktion 3 - Seminarinformationen senden:** Erstelle eine weitere E-Mail-Action. Das Template enthält Anfahrt, Zeitplan, was mitzubringen ist und ggf. Vorbereitungsmaterial
4. **Aktion 4 - Wait (1 Tag vor Event):** Noch eine Wait-Action, diesmal 1 Tag vor dem Event
5. **Aktion 5 - Erinnerung senden:** Die letzte E-Mail erinnert an den morgigen Termin und fasst die wichtigsten Infos zusammen

Die fertige Kette sieht im After-Sales-Bereich so aus:

```
Bei Kauf: E-Mail "Buchungsbestätigung"
Bei Kauf: Wait - 2 Wochen vor Event
Bei Kauf: E-Mail "Seminarinformationen"
Bei Kauf: Wait - 1 Tag vor Event
Bei Kauf: E-Mail "Erinnerung"
```

:::tip[Tipp]
Erstelle die E-Mail-Templates zuerst unter **E-Mails**, bevor du die Delivery Actions einrichtest. So kannst du sie direkt im Dropdown auswählen.
:::

## Erfolgs- und Fehlermeldungen

Nexus protokolliert den Status jeder ausgeführten Delivery Action:

- **Delivery Log** - unter **Einstellungen > Logs > Delivery Log** siehst du alle ausgeführten Actions mit Zeitstempel, Status und Details
- **In der Bestellung** - im Bestelldetail unter **Delivery-Status** siehst du, welche Actions erfolgreich waren und welche fehlgeschlagen sind
- **Bei Fehlern** - Nexus versucht fehlgeschlagene Actions automatisch erneut (Retry). Die Anzahl der Retries ist konfigurierbar
- **Typische Fehlerquellen:** SMTP-Timeout, Webhook-Ziel nicht erreichbar, ungültiges E-Mail-Template

:::warning[Wichtig]
Prüfe den Delivery Log regelmäßig, besonders nach dem Einrichten neuer Automations. So erkennst du Fehler frühzeitig und kannst sie beheben.
:::

## Retry-Logik

Falls eine Action fehlschlägt (z.B. Webhook-Timeout oder SMTP-Fehler), versucht Nexus es automatisch erneut. Den Status jeder einzelnen Action siehst du in den Bestelldetails unter **Delivery-Status**.
