---
title: Datenschutzerklaerung
order: 2
excerpt: DSGVO-konforme Datenschutzerklaerung einrichten
---

# Datenschutzerklärung

Jede Website in der EU braucht eine Datenschutzerklärung (DSGVO Art. 13). Spotlight liefert dir eine Vorlage, die du an deine Situation anpasst.

## Was in die Datenschutzerklärung gehört

- **Verantwortlicher** — Name und Kontakt (gleicher wie im Impressum)
- **Welche Daten erhoben werden** — Server-Logs, Cookies, Kontaktformular
- **Zweck der Verarbeitung** — Warum diese Daten?
- **Rechtsgrundlage** — Welcher DSGVO-Artikel?
- **Speicherdauer** — Wie lange werden Daten aufbewahrt?
- **Rechte der Betroffenen** — Auskunft, Löschung, Widerspruch
- **Drittanbieter** — Alle externen Dienste (Google Analytics, Brevo, Cloudflare etc.)

## Datenschutz-Seite anlegen

1. **Seiten > Neue Seite**
2. Titel: `Datenschutzerklärung`
3. Slug: `datenschutz`
4. Vorlage einfügen (siehe unten)
5. **Veröffentlichen**

## Was bei Spotlight automatisch passiert

Die folgenden Punkte gelten für jede Spotlight-Website — übernimm sie in deine Datenschutzerklärung:

### Hosting bei Hetzner (Deutschland)

> Unsere Website wird bei der Hetzner Online GmbH in Deutschland gehostet. Im Rahmen des Aufrufs werden Server-Logfiles erstellt (IP-Adresse, Datum, User-Agent), die nach 7 Tagen automatisch gelöscht werden.

### SSL-Verschlüsselung

> Alle Verbindungen zu dieser Website sind TLS-verschlüsselt (HTTPS).

### Keine Cookies ohne Einwilligung

> Es werden nur technisch notwendige Cookies ohne Einwilligung gesetzt. Alle weiteren Cookies (Statistik, Marketing) werden erst nach expliziter Einwilligung über unseren Cookie-Banner geladen.

### Kontaktformular

> Wenn Sie uns per Kontaktformular Anfragen zukommen lassen, werden Ihre Angaben aus dem Anfrageformular inklusive der von Ihnen dort angegebenen Kontaktdaten zwecks Bearbeitung der Anfrage und für den Fall von Anschlussfragen bei uns gespeichert.

## Vorlage

Wir empfehlen den [Generator von e-recht24.de](https://www.e-recht24.de/muster-datenschutzerklaerung.html) oder [Dr. Schwenke](https://datenschutz-generator.de/). Beide sind kostenlos und berücksichtigen DSGVO + TTDSG.

Nach dem Generieren:

1. Text kopieren
2. Neue Seite in Spotlight anlegen
3. HTML-Override öffnen, Text einfügen
4. Veröffentlichen

## Im Footer verlinken

```html
<footer>
  <a href="/impressum">Impressum</a> ·
  <a href="/datenschutz">Datenschutz</a> ·
  <a href="#" onclick="window.spotlightConsent.open(); return false;">Cookie-Einstellungen</a>
</footer>
```

## Auftragsverarbeitungsvertrag (AVV)

Falls du Spotlight gewerblich nutzt, schließen wir auf Anfrage einen AVV mit dir ab. Schreib eine Mail an [support@startandconnect.com](mailto:support@startandconnect.com) — du bekommst den AVV innerhalb eines Werktags zur Unterschrift.
