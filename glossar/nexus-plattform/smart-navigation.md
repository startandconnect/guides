---
title: Smart Navigation
order: 19
excerpt: Individuelles HTML-basiertes Header und Footer
---

# Smart Navigation

Individueller Header + Footer der je nach User-Status (Visitor / Customer / Team) unterschiedliche Navigation zeigt. Implementiert auf startandconnect.com.

## Der Mechanismus

Drei Varianten werden gespeichert:
- **visitor.html** - fuer nicht-eingeloggte Besucher
- **customer.html** - fuer eingeloggte Kunden
- **team.html** - fuer eingeloggte Admins

Server bestimmt aus Auth-Cookie welche Variante zu rendern ist. Diese wird als [HTML-Override](/glossar/nexus-plattform/html-override) eingebunden.

## Was typisch unterschiedlich ist

- **Visitor**: Login-Button, Produkt-Menu, Blog-Link
- **Customer**: "Mein Konto"-Link, Order-Shortcut, Logout
- **Team**: "Dashboard"-Link, Admin-Bereich-Shortcut, User-Dropdown

## Vorteile

- **Keine Login-Flags in einem Single-HTML** - kein Flackern beim Hydration
- **Server-rendered** - kein Client-Seiten-Swap
- **SEO-freundlich** - Visitor-Variante wird gecached und ausgeliefert

## Wie konfigurieren

Admin unter `/manage/settings/navigation`. Drei HTML-Editoren (einer pro Variante) plus Footer-Override gleicher Struktur.

## Smart-Nav auf startandconnect.com

Konkrete Implementation:
- **Visitor**: "Produkte / Services / Hosting / Workshops / Aktuelles" + Dashboard-Login-Button
- **Customer**: wie Visitor plus "Dashboard"-Shortcut mit User-Menu
- **Team**: wie Customer plus direkter "Manage"-Shortcut

Im HTML ist auch Theme-Toggle, Shopping-Cart-Anzeige und Custom-Animations.

## Payload-Optimierung

Bei jedem Public-Page-Load wurde historisch alle 3 Varianten mitgeschickt (obwohl nur eine gerendert wird). Seit v1.3.77 nutzt der Server den Query-Param `?status=visitor` und reduziert den Payload auf nur die aktive Variante.

## SSR-Rendering

Der HTML-Content wird nicht per Client-Effect-Hook eingesetzt sondern direkt im SSR-Output via `dangerouslySetInnerHTML`. Seit v1.3.77. Vorher: leerer `<div ref />` der per DOMParser befuellt wird → sichtbarer Pop-in beim Laden. Jetzt: Header ist im Initial-HTML, kein Flackern mehr.

## Setup-Aufwand

Smart Navigation aufzusetzen braucht HTML/CSS-Skills. Fuer viele Kunden ist der Standard-PublicHeader voellig ausreichend. Die Option ist da wenn du sie brauchst.
