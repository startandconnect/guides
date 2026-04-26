---
title: Online-Kurs verkaufen
order: 3
excerpt: Digitale Kurse erstellen, verkaufen und automatisiert ausliefern
---

# Online-Kurs verkaufen

Du hast einen Online-Kurs erstellt und willst ihn verkaufen? Nexus macht das einfach: Produkt anlegen, Preis setzen, Delivery einrichten - fertig. Deine Kunden kaufen, bekommen automatisch Zugang und können ihre Inhalte im Kundenportal abrufen.

## Schritt 1: Produkt anlegen

1. Gehe zu **Produkte > Neues Produkt**
2. Wähle den Typ **PRODUCT**
3. Gib einen Titel ein (z.B. "SEO Masterclass 2024")
4. Füge eine Beschreibung hinzu, die den Kursinhalt beschreibt
5. Lade ein Produktbild hoch

## Schritt 2: Preis setzen

Entscheide dich für ein Preismodell:

- **Einmalkauf:** Der Kunde zahlt einmal und hat dauerhaft Zugang
- **Abo:** Der Kunde zahlt monatlich oder jährlich (ideal für laufend aktualisierte Inhalte)
- **Ratenzahlung:** Über Stripe kannst du Ratenzahlung anbieten

Klicke auf **Preis hinzufügen** und konfiguriere Betrag, Währung und Abrechnungsintervall.

:::tip[Tipp]
Biete einen Einmalkauf und ein Abo parallel an. So können Kunden wählen, ob sie sofort den vollen Preis zahlen oder monatlich.
:::

## Schritt 3: Kursinhalte als Downloads hinterlegen

Lade deine Kursmaterialien in die Mediathek hoch:

1. Gehe zu **Mediathek** und lade alle Dateien hoch (Videos, PDFs, Workbooks)
2. Gehe zurück zu deinem Produkt
3. Unter **Downloads** fügst du die relevanten Dateien hinzu
4. Kunden können diese nach dem Kauf im Kundenportal herunterladen

## Schritt 4: Delivery Action einrichten

Nach dem Kauf soll der Kunde automatisch seine Zugangsdaten erhalten:

1. Oeffne dein Produkt und wechsle zum Bereich **After-Sales**
2. Erstelle eine neue Action mit dem Trigger **Bei Kauf**
3. Wähle als Aktion **E-Mail senden**
4. Erstelle ein E-Mail Template mit:
   - Begrüßung und Danke
   - Link zum Kundenportal
   - Zugangsdaten (falls externer Kursbereich)
   - Kontakt für Fragen

::: tip[Tipp]
Wenn du ueber-Produkt-greifende Workflows brauchst (z.B. CRM-Tagging, externe Webhooks, mehrstufige Mail-Sequenzen), nutze stattdessen das Automations-System unter **Automations** in der Sidebar. Siehe [Automationen](../features/automatisierung.md).
:::

## Schritt 5: Erfolgsseite konfigurieren

Nach dem Kauf landet der Kunde auf einer Erfolgsseite:

1. Gehe zu deinem Produkt unter **Checkout > Erfolgsseite**
2. Passe die Nachricht an (z.B. "Vielen Dank! Dein Kurs wartet auf dich.")
3. Füge einen Button zum Kundenportal hinzu
4. Optional: Zeige direkt den ersten Download an

## Schritt 6: Kundenportal einrichten

Im Kundenportal sehen deine Kunden ihre gekauften Produkte und Downloads:

1. Gehe zu **Einstellungen > Portal**
2. Aktiviere das Kundenportal
3. Passe das Branding an (Logo, Farben)
4. Prüfe, ob Downloads korrekt angezeigt werden

Kunden loggen sich über einen Magic Link ein - kein Passwort nötig.

:::info[Hinweis]
Das Kundenportal ist automatisch unter deiner Domain erreichbar (z.B. `meinedomain.de/portal`). Kunden sehen dort alle ihre Käufe, Downloads und Rechnungen.
:::

## Schritt 7: Community-Zugang einrichten (Optional)

Wenn du deinen Kursteilnehmern eine Community bieten willst:

1. Aktiviere das **Circle Plugin** unter **Plugins**
2. Verbinde deinen Circle-Space
3. Konfiguriere unter **Produkt > After-Sales** eine Delivery Action, die neue Käufer automatisch zur Community einlädt
4. Kunden erhalten nach dem Kauf eine Einladung per E-Mail

## Schritt 8: Newsletter-Anmeldung nach Kauf (Optional)

Halte den Kontakt zu deinen Kunden:

1. Aktiviere das **Newsletter Plugin**
2. Gehe zu **Automations > Rules** und erstelle eine neue Rule
3. Trigger: `ORDER_PAID`
4. Action: `ADD_TO_LIST` mit deinem Newsletter-Segment (z.B. "Kurs-Teilnehmer")

:::warning[Wichtig]
Informiere in deiner Datenschutzerklärung darüber, dass Käufer zum Newsletter hinzugefügt werden. Alternativ kannst du die Anmeldung als Opt-In im Checkout anbieten.
:::

## Zusammenfassung

| Was | Wo |
|-----|-----|
| Produkt anlegen | Produkte > Neues Produkt |
| Preis setzen | Produkt > Preise |
| Downloads | Mediathek + Produkt > Downloads |
| Automatische E-Mail | Produkt > After-Sales (oder Automations) |
| Kundenportal | Einstellungen > Portal |
| Community | Plugins > Circle |
| Newsletter | Plugins > Newsletter |
