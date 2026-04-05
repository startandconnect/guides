---
title: Brevo
order: 10
excerpt: Kontakt-Sync und Listen-Zuordnung mit Brevo (ehemals Sendinblue)
---

# Brevo

Synchronisiere deine Nexus-Kunden automatisch mit Brevo (ehemals Sendinblue). Nutze Brevo für fortgeschrittene E-Mail-Automation, Kampagnen und Marketing-Workflows.

## API Key konfigurieren

1. Gehe zu **Einstellungen > Plugins > Brevo**
2. Trage deinen Brevo API Key ein (findest du in Brevo unter SMTP & API > API Keys)
3. Speichere die Einstellungen
4. Nexus prüft die Verbindung automatisch

:::info[Hinweis]
Du brauchst einen Brevo-Account mit aktiviertem API-Zugang. Der kostenlose Brevo-Plan reicht für den Start.
:::

## Kontakt-Sync

Nach der Konfiguration werden Nexus-Kunden automatisch mit Brevo synchronisiert:

- **Neue Kunden** - Werden automatisch als Kontakte in Brevo angelegt
- **Aktualisierte Daten** - Änderungen an E-Mail, Name oder anderen Feldern werden synchronisiert
- **Bidirektionale Zuordnung** - Nexus speichert die Brevo Contact ID für jeden Kunden

Der Sync läuft im Hintergrund und erfordert kein manuelles Eingreifen.

## Listen-Zuordnung

Ordne deine Kunden automatisch Brevo-Listen zu:

1. Erstelle in Brevo die gewünschten Listen (z.B. "Newsletter", "Kunden", "VIP")
2. In Nexus unter **Einstellungen > Plugins > Brevo** siehst du alle verfügbaren Listen
3. Weise Listen zu - entweder global oder pro Produkt

### Pro Produkt konfigurieren

Die Listen-Zuordnung lässt sich pro Produkt steuern:

- Öffne ein Produkt und gehe zu den Brevo-Einstellungen
- Wähle aus welcher Brevo-Liste der Käufer nach dem Kauf hinzugefügt werden soll
- So landen z.B. Käufer von Kurs A in Liste "Kurs A Teilnehmer" und Käufer von Kurs B in Liste "Kurs B Teilnehmer"

:::tip[Tipp]
Nutze produktbasierte Listen um in Brevo automatisierte Follow-up Kampagnen pro Produkt aufzusetzen. Käufer erhalten so passende Upselling-Angebote.
:::

## Kampagnenmanagement

Die eigentlichen E-Mail-Kampagnen erstellst und versendest du in Brevo. Nexus liefert die Kontakte und Listen-Zuordnungen, Brevo übernimmt den Versand:

- Erstelle Kampagnen im Brevo Dashboard
- Nutze die von Nexus synchronisierten Listen als Empfänger
- Profitiere von Brevos Template-Editor und A/B-Testing

## Automation-Workflows

Brevo bietet leistungsstarke Automation-Workflows die du mit den Nexus-Daten füttern kannst:

- **Willkommens-Workflow** - Trigger wenn ein neuer Kontakt einer Liste hinzugefügt wird
- **Nach-Kauf-Serie** - Automatische E-Mail-Serie basierend auf der Produkt-Liste
- **Re-Engagement** - Inaktive Kontakte reaktivieren

Die Workflows konfigurierst du direkt in Brevo. Nexus sorgt dafür dass die Kontakte zur richtigen Zeit in der richtigen Liste landen.
