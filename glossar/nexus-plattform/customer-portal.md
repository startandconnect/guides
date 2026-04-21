---
title: Customer Portal
order: 7
excerpt: Der eingeloggte Bereich fuer deine Kunden
---

# Customer Portal

Der Bereich unter `/customer/*` fuer eingeloggte Kaeufer. Hier sehen deine Kunden ihre Bestellungen, Abos, Downloads, Rechnungen.

## Was Kunden im Portal finden

- **Overview** (`/customer/overview`) - Willkommens-Dashboard mit Quick-Access
- **Orders** (`/customer/orders`) - alle Bestellungen mit Status
- **Subscriptions** (`/customer/subscriptions`) - aktive Abos, Kuendigungsmoeglichkeit
- **Invoices** (`/customer/invoices`) - PDF-Download
- **Downloads** (`/customer/downloads`) - Digitale Produkte zum Runterladen
- **Events** (`/customer/events`) - gebuchte Events, Teilnehmer-Daten
- **Shared Files** (`/customer/shared-files`) - Dateien die du dem Kunden geteilt hast
- **Wishlist** (`/customer/wishlist`) - falls Wishlist-Plugin aktiv
- **Meine Produkte** (`/customer/products`) - gekaufte Produkte
- **Notifications** - System-Benachrichtigungen
- **Messages** - Kommunikation mit dir / Support
- **Account** - Profil-Settings, Password aendern

## Individuelles Branding

Customer Portal nutzt dein Theme, dein Logo, deine Farben. Fuer Kunden fuehlt sich das an wie ein integraler Teil deiner Marke - nicht wie eine separate Software.

## Abgeklemmt vom Admin

Kunden haben `CUSTOMER`-Rolle. Sie haben keinerlei Zugang zu `/manage`. Absolute Datenisolation: ein Kunde sieht NUR seine eigenen Daten, auch wenn er versucht URLs zu manipulieren (Scope-Filter im Backend verhindert cross-customer-Access).

## Login + Registrierung

- Kunden registrieren sich beim Kauf automatisch (mit Email + Passwort setzen)
- Alternativ: Registrierung ueber Newsletter-Anmeldung + spaeterer Kauf
- Passwort-Reset per Email-Link

## Welche Portal-Features hat jede Instance

Nicht alle Instances zeigen alle Portal-Seiten. Events nur wenn Events-Plugin aktiv, Shared-Files nur wenn konfiguriert. Admin entscheidet pro Plugin ob Customer-Portal-Seite sichtbar.

## Support-Kontakt

Messages-Tab erlaubt bi-direktionale Kommunikation zwischen Kunde und Support-Team. Mit Ticket-Workflow, Status-Tracking.
