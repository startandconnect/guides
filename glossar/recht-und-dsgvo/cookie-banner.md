---
title: Cookie-Banner
order: 8
excerpt: Einwilligung fuer Tracking
---

# Cookie-Banner

Einwilligungs-Dialog der Nutzern die Wahl gibt welche Cookies sie erlauben. Pflicht fuer alle nicht-essentiellen Cookies.

## Was muss ins Banner

- **Transparente Info** - welche Cookies, welcher Zweck, welche Anbieter
- **Aktive Zustimmung** erforderlich fuer nicht-essentielle Cookies (Default-off)
- **Ablehnung** genauso einfach wie Zustimmung (kein "Akzeptieren-Button" hervorheben, "Ablehnen" verstecken)
- **Widerruf** jederzeit moeglich
- **Granularitaet** pro Kategorie (essentielle, Analytics, Marketing)

## Essentielle vs nicht-essentielle Cookies

**Essentiell** (keine Einwilligung noetig):
- Session-Cookies fuer Login
- Warenkorb-Cookies
- Language-Preference
- CSRF-Tokens

**Nicht-essentiell** (Einwilligung erforderlich):
- Google Analytics
- Facebook-Pixel
- Marketing-Tracking
- A/B-Test-Tools (oft)
- Chat-Widgets mit Tracking

## Technische Umsetzung

Bis zur Zustimmung: **KEIN Tracking laden**. Nicht nur auf Default-off setzen - Scripts duerfen erst nach Consent ausgefuehrt werden.

Nexus-Cookie-Banner:
- SSR-gerendert (kein Flicker beim Laden)
- Drei Optionen: Alle akzeptieren, Alle ablehnen, Individuell einstellen
- Wahl wird als Cookie gespeichert (`cookieConsent`)
- Andere Scripts erst nach Consent geladen

## Opt-In vs Opt-Out

**Opt-In** (EU-Standard): nicht-essentielle Cookies nur mit aktiver Zustimmung.

**Opt-Out** (US-Standard): Cookies laufen standardmaessig, User kann ablehnen.

EU-DSGVO + EuGH-Rechtssprechung verlangen klar Opt-In. Opt-Out ist illegal fuer Tracking.

## Consent-Mode (Google)

Google-Analytics-Feature das Tracking nur durchfuehrt wenn User zugestimmt hat. Setzt automatisch "analytics_storage": "denied" bis Consent kommt.

Nexus-Cookie-Banner-Integration setzt Consent-Mode automatisch basierend auf Nutzer-Auswahl.

## Consent-Management-Plattformen (CMP)

Spezialisierte Tools wie Cookiebot, Usercentrics, CookieFirst. Features:
- Auto-Scan der Website nach Cookies
- Mehrsprachige Banner
- Consent-Log-Datenbank
- Updates bei neuen Rechtsprechungen

Nexus-Cookie-Banner ist fuer Standard-Shops ausreichend. Fuer komplexe Setups (viele Third-Party-Tools) lohnt sich externe CMP.

## Abmahn-Risiko

Unvollstaendige oder falsche Cookie-Banner werden aktiv abgemahnt. Typisch 500-1500 Euro pro Fall. Wenn Banner komplett fehlt: schnell nachruesten.
