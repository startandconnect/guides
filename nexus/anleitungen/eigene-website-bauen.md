---
title: Eigene Website bauen
order: 6
excerpt: Komplette Website in Nexus erstellen mit Domain, Branding und SEO
---

# Eigene Website bauen

Nexus ist nicht nur ein Shop-System - du kannst damit eine vollständige Website unter deiner eigenen Domain betreiben. Startseite, Unterseiten, Navigation, Legal-Seiten und SEO - alles inklusive. So baust du deine Website Schritt für Schritt auf.

## Schritt 1: Domain verbinden

Zuerst bringst du deine eigene Domain auf Nexus:

1. Gehe zu **Einstellungen > System > Hosting**
2. Trage deine Domain ein (z.B. `meinbusiness.de`)
3. Nexus zeigt dir den CNAME-Eintrag an, den du beim Domain-Registrar setzen musst
4. Gehe zu deinem Domain-Registrar (z.B. Cloudflare, IONOS, Namecheap)
5. Erstelle einen CNAME-Eintrag mit dem angezeigten Wert
6. Warte auf die DNS-Propagation (wenige Minuten bis 24 Stunden)
7. Nexus erstellt automatisch ein SSL-Zertifikat

:::info[Hinweis]
Wenn du Cloudflare nutzt, setze den Proxy-Status auf "DNS only" (graue Wolke), damit das SSL-Zertifikat von Nexus korrekt funktioniert.
:::

## Schritt 2: Branding einrichten

Gib deiner Website ein einheitliches Erscheinungsbild:

1. Gehe zu **Einstellungen > Inhalte > Branding**
2. Lade dein Logo hoch (empfohlen: SVG oder PNG mit transparentem Hintergrund)
3. Setze deine Markenfarben:
   - Primärfarbe (für Buttons und Links)
   - Sekundärfarbe (für Akzente)
   - Hintergrundfarbe
4. Wähle eine Schriftart (Google Fonts werden automatisch lokal gehostet)

## Schritt 3: Startseite erstellen

Die Startseite ist der erste Eindruck. Du hast zwei Optionen:

**Option A - Page Builder:**
1. Gehe zu **Inhalte > Seiten > Startseite**
2. Nutze den visuellen Editor mit Drag-and-Drop-Blöcken
3. Füge Texte, Bilder, Buttons und Produkt-Übersichten hinzu

**Option B - HTML Override:**
1. Gehe zu **Inhalte > Seiten > Startseite**
2. Aktiviere den **HTML Override**
3. Schreibe oder kopiere eigenes HTML und CSS
4. Volle Kontrolle über jedes Detail des Designs

:::tip[Tipp]
HTML Override ist die beste Wahl für individuelle Designs. Du kannst Tailwind CSS oder eigenes CSS verwenden. Templates findest du in der Nexus Community.
:::

## Schritt 4: Weitere Seiten anlegen

Erstelle die Seiten, die dein Business braucht:

1. Gehe zu **Inhalte > Seiten > Neue Seite**
2. Typische Seiten:
   - **Über mich/uns:** Deine Geschichte, Team, Mission
   - **Kontakt:** Kontaktformular (über das Forms Plugin), E-Mail, Adresse
   - **Angebot/Leistungen:** Was du anbietest
   - **FAQ:** Häufig gestellte Fragen
   - **Blog:** Aktiviere das Blog Plugin für regelmäßige Inhalte
3. Nutze für jede Seite den Page Builder oder HTML Override

## Schritt 5: Navigation konfigurieren

Damit Besucher sich zurechtfinden:

1. Gehe zu **Einstellungen > Inhalte > Navigation**
2. Füge Menüpunkte hinzu:
   - Verlinke auf deine erstellten Seiten
   - Verlinke auf den Shop, Blog oder Events
   - Externe Links (z.B. Social Media)
3. Sortiere die Menüpunkte per Drag-and-Drop
4. Optional: Füge einen **CTA Button** hinzu (z.B. "Jetzt kaufen" oder "Kostenlos testen")

## Schritt 6: Legal-Seiten erstellen

In Deutschland sind diese Seiten Pflicht:

1. Gehe zu **Einstellungen > Inhalte > Legal**
2. Erstelle folgende Seiten:
   - **Impressum:** Pflichtangaben nach TMG (Name, Adresse, Kontakt, Steuernummer)
   - **Datenschutzerklärung:** Welche Daten du sammelst und wie du sie verarbeitest
   - **AGB:** Allgemeine Geschäftsbedingungen für deinen Shop

:::warning[Wichtig]
Nutze einen Generator für rechtssichere Legal-Seiten (z.B. eRecht24 oder IT-Recht-Kanzlei) oder lass sie von einem Anwalt erstellen. Kopiere keine fremden Texte.
:::

## Schritt 7: SEO-Grundeinstellungen

Damit deine Website bei Google gefunden wird:

1. **Meta Tags:** Setze für jede Seite einen Title Tag und eine Meta Description
2. **OG Images:** Lade Social-Media-Vorschaubilder hoch (werden angezeigt, wenn deine Seite auf Social Media geteilt wird)
3. **Sitemap:** Nexus generiert automatisch eine Sitemap unter `/sitemap.xml`
4. **Strukturierte Daten:** Produktseiten enthalten automatisch Schema.org Markup

Prüfe deine Seiten mit der Google Search Console, sobald alles live ist.

## Schritt 8: Fertig - alles unter deiner Domain

Deine Website läuft jetzt komplett auf Nexus:

- Website und Shop unter einer Domain
- E-Mails kommen von deiner Domain
- Kundenportal unter deiner Domain
- Kein WordPress, kein separates Shop-System, keine zusätzlichen Tools

| Bestandteil | Status |
|------------|--------|
| Domain verbunden | ☐ |
| Branding eingerichtet | ☐ |
| Startseite erstellt | ☐ |
| Unterseiten angelegt | ☐ |
| Navigation konfiguriert | ☐ |
| Legal-Seiten erstellt | ☐ |
| SEO eingerichtet | ☐ |
