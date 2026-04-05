---
title: Newsletter aufsetzen
order: 5
excerpt: Newsletter von Null einrichten mit Double-Opt-In und ersten Kampagnen
---

# Newsletter aufsetzen

Ein Newsletter ist einer der effektivsten Kanäle für Kundenbindung und Verkäufe. In Nexus ist E-Mail Marketing direkt integriert - kein Mailchimp, kein ConvertKit, keine extra Kosten. So richtest du alles ein.

## Schritt 1: SMTP konfigurieren

Bevor du E-Mails versenden kannst, brauchst du einen SMTP-Provider:

1. Gehe zu **Einstellungen > Kommunikation > E-Mail**
2. Trage deine SMTP-Daten ein:
   - Host (z.B. `smtp.eu.mailgun.org`)
   - Port (587 für TLS)
   - Benutzername und Passwort
   - Absender-E-Mail und Name
3. Klicke auf **Verbindung testen**

:::tip[Tipp]
Wir empfehlen **Mailgun EU** (Frankfurt-Server) für DSGVO-Konformität. Alternative: Amazon SES EU. Vermeide US-basierte Anbieter ohne EU-Server.
:::

## Schritt 2: Newsletter Plugin aktivieren

1. Gehe zu **Plugins > Übersicht**
2. Aktiviere das **Newsletter Plugin**
3. Nach der Aktivierung findest du **Newsletter** im Seitenmenü

## Schritt 3: Double-Opt-In einrichten

Double-Opt-In ist in Deutschland Pflicht. Nexus macht es dir einfach:

1. Gehe zu **Einstellungen > Kommunikation > E-Mail Templates**
2. Bearbeite das Template **Newsletter Bestätigung**
3. Passe den Text an:
   - Begrüße den neuen Subscriber
   - Erkläre kurz, was ihn erwartet
   - Der Bestätigungslink wird automatisch eingefügt
4. Teste das Template mit einer Test-E-Mail

:::warning[Wichtig]
Deaktiviere niemals den Double-Opt-In. Ohne Double-Opt-In verstößt du gegen die DSGVO und riskierst Abmahnungen. Nexus erzwingt Double-Opt-In standardmäßig.
:::

## Schritt 4: Anmeldeformular erstellen

Erstelle ein Formular, über das sich Besucher anmelden können:

1. Aktiviere das **Forms Plugin** unter **Plugins**
2. Gehe zu **Formulare > Neues Formular**
3. Füge Felder hinzu: E-Mail (Pflicht), Vorname (optional)
4. Wähle als Aktion **Zum Newsletter hinzufügen**
5. Binde das Formular auf deiner Website ein (Einbettungscode wird generiert)

Du kannst das Formular auf jeder Seite einbinden - Startseite, Blog, Sidebar oder als Popup.

## Schritt 5: Erste Subscriber importieren

Du hast schon eine E-Mail-Liste? Importiere sie:

1. Gehe zu **Newsletter > Subscriber > Importieren**
2. Lade eine CSV-Datei hoch (Spalten: E-Mail, Vorname, Nachname)
3. Wähle, ob importierte Kontakte den Double-Opt-In durchlaufen sollen

:::info[Hinweis]
Importiere nur Kontakte, die dir nachweislich ihre Einwilligung gegeben haben. Bei der Migration von einem anderen Newsletter-Tool kannst du den Double-Opt-In für bestehende Subscriber überspringen.
:::

## Schritt 6: Erstes Broadcast erstellen

Ein Broadcast ist eine einmalige E-Mail an alle (oder ausgewählte) Subscriber:

1. Gehe zu **Newsletter > Neues Broadcast**
2. Wähle eine Betreffzeile (kurz, konkret, neugierig machend)
3. Schreibe deine E-Mail im Editor
4. Wähle die Empfänger (alle oder ein Segment)
5. Klicke auf **Test senden** und prüfe die E-Mail in deinem Postfach
6. Wenn alles passt: **Jetzt senden** oder **Planen**

## Schritt 7: Segmente anlegen

Segmente ermöglichen dir, gezielte Inhalte an bestimmte Gruppen zu senden:

1. Gehe zu **Newsletter > Segmente**
2. Erstelle Segmente basierend auf:
   - Kaufverhalten (hat Produkt X gekauft)
   - Tags (manuell zugewiesen)
   - Anmeldedatum
3. Nutze Segmente beim Versand von Broadcasts

Beispiele für sinnvolle Segmente:
- "Kurs-Käufer" - Kunden, die deinen Kurs gekauft haben
- "Interessenten" - Subscriber, die noch nichts gekauft haben
- "VIP" - Kunden mit hohem Umsatz

## Schritt 8: Engagement tracken

Nach dem Versand siehst du wichtige Kennzahlen:

| Kennzahl | Guter Wert | Beschreibung |
|----------|-----------|-------------|
| Öffnungsrate | 20-30% | Wie viele haben die E-Mail geöffnet |
| Klickrate | 2-5% | Wie viele haben auf einen Link geklickt |
| Abmelderate | unter 0,5% | Wie viele haben sich abgemeldet |

## Best Practices

- **Betreffzeile:** Maximal 50 Zeichen, konkreten Nutzen versprechen
- **Versandzeit:** Dienstag bis Donnerstag, 9-11 Uhr funktioniert für die meisten Branchen
- **Häufigkeit:** Starte mit 1x pro Woche, steigere bei Bedarf
- **Inhalt:** 80% Mehrwert, 20% Verkauf. Deine Subscriber bleiben, wenn du ihnen hilfst
- **Konsistenz:** Lieber regelmäßig monatlich als unregelmäßig wöchentlich
