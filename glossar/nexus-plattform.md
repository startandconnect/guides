---
title: Nexus Plattform
order: 4
excerpt: Plattform-spezifische Begriffe aus der Nexus-Welt
---

# Nexus Plattform

## Nexus

Die KI-steuerbare Business-Plattform von Start und Connect fuer Verkaeufer digitaler Produkte. Shop, CRM, Analytics, Newsletter, Events, Affiliate - alles in einem System, ueber API und MCP steuerbar.

## Instance (Instanz)

Deine eigene isolierte Nexus-Umgebung. Jede Instance hat ihre eigene Datenbank, Subdomain und Konfiguration. Deine Daten sind vollstaendig von anderen Kunden getrennt (Multi-Tenant mit dedizierter DB).

## Multi-Tenant

Architektur, bei der mehrere Kunden dasselbe System nutzen, aber ihre Daten isoliert sind. Nexus ist Multi-Tenant mit **eigener Datenbank pro Kunde**.

Vorteil: starke Isolation, DSGVO-konform, individuelle Backups.

## Plugin

Erweiterungs-Modul fuer Nexus. Erweitert die Basis-Funktionalitaet ohne Plattformwechsel. Plugins liefern Routes, UI-Komponenten, Delivery-Actions, Email-Templates.

Beispiele: `blog`, `newsletter`, `forms`, `events`, `chatbot`, `reviews`, `wishlist`.

## Marketplace

Verzeichnis aller verfuegbaren Nexus-Plugins. Als Admin installierst du Plugins aus dem Marketplace mit einem Klick. Private Plugins (z.B. Kunden-spezifische) sind nicht im Marketplace.

## Portal

Das offene Kunden-Interface deiner Nexus-Instance. Was die Besucher deiner Domain sehen: Shop, Blog, Produkt-Landingpages, Kundenportal. Getrennt vom Admin-Bereich (`/manage`).

## Manage / Admin Dashboard

Der eingeloggte Admin-Bereich unter `/manage`. Hier verwaltest du Produkte, Kunden, Bestellungen, Settings. Zugriff nur fuer Team-Mitglieder mit entsprechenden Rollen.

## Customer Portal

Der eingeloggte Kunden-Bereich unter `/customer/*`. Kunden sehen ihre Bestellungen, Abos, Downloads, Rechnungen.

## Role (Rolle)

Bestimmt welche Aktionen ein Nutzer ausfuehren darf. Nexus-Kern-Rollen: `OWNER`, `ADMIN`, `SUPER_ADMIN`, `MEMBER`, `SELLER`, `SUPPORT`, `ACCOUNTANT`, `CUSTOMER`.

## Permission

Einzelne Berechtigung wie `orders.create` oder `customers.delete`. Rollen haben vordefinierte Permission-Sets. Custom-Rollen mit individuellen Permissions sind moeglich.

## Scope

Wie weit die Permission reicht: alle Daten, nur eigene, Team-weit, oder nichts. Nexus hat 4 Scopes: `all`, `team`, `own`, `none`. Die Scope-Matrix unter Einstellungen > Rollen erlaubt feingranulare Konfiguration.

## Delivery Action

Eine Aktion, die nach einem Event (Kauf, Eventbuchung, Abo-Start) ausgefuehrt wird. Typische Delivery-Actions: "Willkommens-Email senden", "Kurs freischalten", "Slack-Nachricht posten", "WAIT 7 Tage".

## Automation

Sequenz von Delivery-Actions mit bedingter Logik. Wie ein Marketing-Automation-Flow, aber direkt an Produkte und Kunden-Events angebunden.

## Trigger

Event, das eine Automation oder Delivery-Action startet. Beispiele: `PURCHASE` (Kauf bezahlt), `BEFORE_EVENT` (vor Event-Termin), `SUBSCRIPTION_ENDED`, `REFUND`.

## HTML Override

Feature, mit dem du eigene HTML/CSS/JS-Inhalte in Nexus-Seiten einfuegst (Homepage, CMS-Pages, Nav, Footer). Fuer komplette Design-Freiheit ohne Plattform-Wechsel.

## Smart Navigation

Individuelles HTML-basiertes Header/Footer, das je nach User-Status (visitor / customer / team) unterschiedliche Navigation anzeigt. Auf startandconnect.com live.

## Scope-Matrix

Admin-UI unter `/settings/access/roles`, in der du pro Rolle x Resource x Aktion den Scope einstellst. Beispiel: SELLER darf Orders lesen, aber nur `own` (nur die Orders wo er als Verkaeufer eingetragen ist).

## Audit-Log

Protokoll aller Datenaenderungen in Nexus: wer hat wann was geaendert. Automatisch aktiv fuer 11 kritische Resources (Order, Product, Customer, Invoice, Subscription etc.). Einsehbar pro Entity-Detail-Seite.

## Dokploy

Deployment- und Container-Management-Tool, das Nexus-Instanzen automatisch deployt und verwaltet. Auf Hetzner-Servern. Admins interagieren selten direkt damit.
