---
title: Migration von WordPress
order: 1
excerpt: Schritt für Schritt von WordPress zu Nexus wechseln
---

# Migration von WordPress

Du willst raus aus WordPress? Gute Entscheidung. Nexus vereint Website, Shop, E-Mail und Kundenverwaltung in einem System - ohne Plugin-Chaos, ohne ständige Updates, ohne Sicherheitslücken. Hier erfährst du, wie du den Umzug sauber durchführst.

## Vorher: Was du brauchst

- Einen aktiven Nexus-Account
- Zugang zu deinem WordPress-Admin-Panel
- Zugang zu deinem Domain-Registrar (z.B. IONOS, Cloudflare, Namecheap)
- Falls vorhanden: Zugang zu deinem Stripe-Dashboard

## Schritt 1: Produkte in Nexus anlegen

Erstelle deine Produkte und Preise in Nexus. Du hast zwei Möglichkeiten:

- **Manuell:** Gehe zu **Produkte > Neues Produkt** und lege jedes Produkt einzeln an. Setze Typ, Preis und Beschreibung.
- **Per Stripe Import:** Wenn du bereits Stripe mit WordPress nutzt, importiere deine bestehenden Produkte direkt. Gehe dazu zu **Einstellungen > Zahlungen > Stripe Import** und wähle die Merge-Strategie.

:::tip[Stripe Import nutzen]
Wenn du Stripe bereits mit WordPress verwendet hast, nutze unbedingt den Stripe Import. So werden Produkte, Preise und bestehende Abos automatisch übernommen.
:::

## Schritt 2: Kunden importieren

Deine bestehenden Kunden müssen mit umziehen:

- **Stripe Import:** Bei der Merge-Strategie werden Kunden automatisch mit ihren Abos und Zahlungsdaten importiert. Das ist der einfachste Weg.
- **CSV Import:** Exportiere deine Kundenliste aus WordPress (z.B. über WooCommerce) als CSV und importiere sie unter **Kunden > Importieren**.

## Schritt 3: Inhalte migrieren

Deine WordPress-Seiten kannst du in Nexus als Seiten nachbauen:

1. Gehe zu **Inhalte > Seiten**
2. Erstelle eine neue Seite
3. Nutze den **Page Builder** für einfache Layouts oder **HTML Override** für maximale Kontrolle
4. Kopiere Texte und Bilder aus deinen WordPress-Seiten

:::info[Hinweis]
Nexus ist kein Blog-System wie WordPress. Für Blog-Inhalte nutze das Blog Plugin, das Markdown und Rich Text unterstützt.
:::

## Schritt 4: Domain umziehen

Jetzt verbindest du deine Domain mit Nexus:

1. Gehe in Nexus zu **Einstellungen > System > Hosting**
2. Trage deine Domain ein (z.B. `meinedomain.de`)
3. Erstelle bei deinem Domain-Registrar einen **CNAME-Eintrag**, der auf deine Nexus-Instanz zeigt
4. Nexus zeigt dir den genauen Wert für den CNAME-Eintrag an

## Schritt 5: SSL-Zertifikat

Sobald der DNS-Eintrag aktiv ist, erstellt Nexus automatisch ein SSL-Zertifikat über Let's Encrypt. Das dauert in der Regel wenige Minuten. Du musst nichts weiter tun.

## Schritt 6: Alte WordPress-Seite deaktivieren

Wenn alles in Nexus läuft und die Domain korrekt zeigt:

1. Prüfe, ob alle Seiten und Produkte erreichbar sind
2. Teste den Checkout-Prozess einmal durch
3. Deaktiviere dein WordPress-Hosting oder schalte die Seite in den Wartungsmodus
4. Kündige nach einer Übergangsphase (ca. 2-4 Wochen) dein altes Hosting

:::warning[Wichtig]
Deaktiviere WordPress erst, wenn du sicher bist, dass alles in Nexus funktioniert. Teste insbesondere den Kaufprozess und E-Mail-Versand.
:::

## Schritt 7: Redirects einrichten

Damit alte Links aus Google und Bookmarks weiterhin funktionieren:

1. Erstelle in Nexus Seiten mit denselben URLs wie in WordPress
2. Für URLs, die sich geändert haben, richte 301-Redirects ein
3. Prüfe nach ein paar Tagen in der Google Search Console, ob Fehler auftreten

## Checkliste nach der Migration

| Aufgabe | Erledigt |
|---------|----------|
| Produkte angelegt | ☐ |
| Kunden importiert | ☐ |
| Seiten erstellt | ☐ |
| Domain verbunden | ☐ |
| SSL aktiv | ☐ |
| Checkout getestet | ☐ |
| E-Mails getestet | ☐ |
| Alte Seite deaktiviert | ☐ |
| Redirects eingerichtet | ☐ |
