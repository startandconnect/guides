---
title: Manage (Admin Dashboard)
order: 6
excerpt: Der eingeloggte Admin-Bereich
---

# Manage (Admin Dashboard)

Der Bereich unter `/manage` in deiner Nexus-Instance. Hier verwaltest du alles - Produkte, Kunden, Bestellungen, Newsletter, Settings. Zugriff nur fuer Team-Mitglieder mit entsprechender Rolle.

## Wer hat Zugriff

Alle Rollen ausser `CUSTOMER`. Das sind Nexus-Kern-Rollen:
- `OWNER` - du selbst, voller Zugriff
- `ADMIN` - alle Admin-Rechte ausser Billing + Team-Verwaltung
- `SUPER_ADMIN` - wie ADMIN aber inkl. Team
- `MEMBER` - eingeschraenkter Zugriff je nach Scope
- `SELLER` - sieht nur eigene Orders + Commissions
- `SUPPORT` - darf Kunden betreuen aber nicht verkaufen
- `ACCOUNTANT` - darf Invoices + Payments sehen

Pro Rolle sind Permissions + Scopes in der Scope-Matrix konfigurierbar.

## Struktur

- **Dashboard** - Uebersicht mit Stats + Widgets
- **Produkte** - CRUD, Kategorien, Coupons, Subscriptions
- **Kunden / Contacts** - CRM, Segmente, Listen, Deals, Aktivitaeten
- **Bestellungen** - Orders, Invoices, Payments, Refunds
- **Inhalte** - CMS-Pages, Blog, Media-Library
- **Kommunikation** - Messages, Emails, Newsletter, Notifications
- **Plugins** - Plugin-spezifische Bereiche (events, forms, chatbot...)
- **Einstellungen** - Settings fuer alles (Branding, Stripe, SMTP, Rollen, API-Keys...)

## Navigation

Linke Sidebar pro Sektion. Sub-Navigation in Tabs pro Detail-Seite.

## Command Palette (Cmd+K)

Schneller Zugang zu allem per Tastatur. Oeffnet sich mit Cmd+K (Mac) oder Ctrl+K (Win).
- Fuzzy-Suche ueber alle Seiten
- Quick-Actions (Neues Produkt / Gutschein / Seite...)
- Entity-Search (Kunden, Produkte, Orders)
- Recent Items (letzte 5 besuchte Seiten)

## Live-Updates via SSE

Neue Bestellung, Newsletter-Status, Import-Progress - alles live sichtbar ohne Reload.

## Audit Log

Alle aendernden Aktionen werden protokolliert. Pro Detail-Seite siehst du unter "Aenderungs-Historie" wer was wann geaendert hat.
