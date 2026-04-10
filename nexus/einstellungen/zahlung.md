---
title: Zahlung & Rechnungen
order: 4
excerpt: Stripe einrichten, Steuern konfigurieren und Rechnungen verwalten
---

# Zahlung & Rechnungen

Nexus nutzt Stripe als Zahlungsanbieter. Unter **Einstellungen > Zahlung** verbindest du deinen Stripe-Account.

## Stripe einrichten

Trage deine Stripe API Keys ein:

- **Public Key** - Beginnt mit `pk_test_` oder `pk_live_`
- **Secret Key** - Beginnt mit `sk_test_` oder `sk_live_`

### Test vs. Live Modus

Nutze zuerst den **Test-Modus** (`pk_test_` / `sk_test_`), um Zahlungen ohne echtes Geld zu testen. Wechsle erst zu Live Keys, wenn alles funktioniert.

:::warning[Wichtig]
Veröffentliche niemals deinen Secret Key. Er gehört nur in die Nexus-Einstellungen, nicht in Frontend-Code oder öffentliche Repositories.
:::

### Webhook-Konfiguration

Nexus benötigt einen Stripe Webhook, um Zahlungsstatus-Updates zu erhalten. Am einfachsten:

1. Gehe in Nexus zu **Einstellungen > Zahlung > Stripe**
2. Klicke auf **Webhook erstellen** - Nexus legt den Webhook automatisch an mit allen 20 benötigten Events
3. Trage den angezeigten **Signing Secret** ein und speichere

Falls du den Webhook manuell in Stripe anlegen möchtest:

1. Erstelle in Stripe unter **Developers > Webhooks** einen neuen Endpoint
2. URL: `https://deinportal.de/api/webhooks/stripe`
3. Wähle alle relevanten Events (Nexus benötigt 20 Events inkl. `checkout.session.completed`, `charge.failed`, `charge.refunded`, `invoice.paid` und weitere)
4. Kopiere den **Signing Secret** und trage ihn in Nexus ein

### 3D Secure

3D Secure (SCA) wird automatisch ausgelöst, wenn die Bank des Käufers es verlangt. Keine zusätzliche Konfiguration nötig.

## Zahlungsmethoden

Über Stripe stehen folgende Methoden zur Verfügung:

- Kreditkarte (Visa, Mastercard, Amex)
- PayPal
- Klarna (Rechnung, Ratenzahlung)
- SEPA-Lastschrift
- Apple Pay / Google Pay

Aktiviere die gewünschten Methoden in deinem Stripe Dashboard unter **Settings > Payment methods**.

## Steuern

- **Standard-Steuersatz** - z.B. 19% MwSt (Deutschland) oder 7.7% (Schweiz)
- **USt-ID** - Deine Umsatzsteuer-Identifikationsnummer für Rechnungen

## Rechnungen

- **Prefix** - Vorangestellter Text für Rechnungsnummern (z.B. `INV-` oder `RE-`)
- **Nummernkreis** - Fortlaufende Nummerierung, startet bei dem von dir gewählten Wert

:::tip[Tipp]
Wähle einen Prefix, der zu deinem Unternehmen passt. Der Nummernkreis zählt automatisch hoch und kann nicht zurückgesetzt werden.
:::

## Fehlgeschlagene Zahlungen

Nexus kann dich und deine Kunden automatisch per E-Mail benachrichtigen, wenn eine Zahlung fehlschlägt - z.B. bei einer SEPA-Rückbuchung oder abgelehnten Kreditkarte.

Konfiguriere die Benachrichtigungen unter **Einstellungen > Zahlung > Stripe** im Abschnitt **Fehlgeschlagene Zahlungen**:

- **Admin benachrichtigen** - Du bekommst eine E-Mail mit allen Details (Bestellnummer, Kunde, Fehlercode, Betrag). Optional kannst du eine eigene E-Mail-Adresse eintragen, sonst wird die Support-E-Mail deines Portals verwendet.
- **Kunden benachrichtigen** - Der Kunde bekommt eine informative E-Mail mit dem Hinweis, sich bei dir zu melden.

Beide Optionen sind standardmässig deaktiviert. Die E-Mail-Inhalte kannst du unter **E-Mails** anpassen (Templates: "Zahlung fehlgeschlagen (Admin)" und "Zahlung fehlgeschlagen (Kunde)").

Nexus erkennt automatisch fehlgeschlagene Zahlungen, auch wenn sie erst Tage später scheitern (z.B. SEPA-Lastschriften die von der Bank zurückgebucht werden). Bestellungen werden in diesem Fall automatisch auf den Status **FAILED** gesetzt.

## Refund-Policy

Konfiguriere, ob und wie Rückerstattungen möglich sind. Rückerstattungen werden direkt über Stripe abgewickelt - du kannst sie im Nexus Admin-Bereich oder im Stripe Dashboard auslösen.
