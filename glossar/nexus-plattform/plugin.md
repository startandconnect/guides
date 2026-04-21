---
title: Plugin
order: 3
excerpt: Erweiterungs-Module fuer Nexus
---

# Plugin

Erweiterung fuer Nexus. Liefert zusaetzliche Features - Routes, UI-Komponenten, Delivery-Actions, Email-Templates - ohne dass du die Plattform verlassen musst.

## Warum Plugin-System

- **Spezialisierung** - nicht jeder Kunde braucht Events, nicht jeder braucht Newsletter. Plugins aktivieren pro Instance.
- **Eigenstaendige Updates** - Blog-Plugin kann unabhaengig vom Core updated werden
- **Multi-Tenant-Diversitaet** - SUYL hat andere Plugins aktiv als SAC
- **Erweiterbar** - Kunden koennen Custom-Plugins schreiben lassen

## Kern-Plugins (von SAC)

| Plugin | Was es macht |
|---|---|
| **blog** | Blog-Posts mit Scheduled-Publishing, Tags, SEO |
| **newsletter** | Segment-Engine, Bulk-Email, DOI-Flow, Tracking |
| **forms** | Lead-Capture-Formulare mit Automationen |
| **events** | Termin-Buchung, Tickets, Registrierungen |
| **reviews** | Produktbewertungen mit Moderation |
| **wishlist** | Merkliste fuer Customer-Portal |
| **chatbot** | KI-Chatbot mit Knowledge-Base |
| **seller** | Multi-Seller-Marketplace mit Commissions |
| **brevo-integration** | SMTP + Transactional Email |
| **circle-integration** | Circle-Community OAuth + User-Sync |
| **guide** | Markdown-Docs aus Git-Repo (das hier wird davon gerendert) |

## Plugin-Struktur

Jedes Plugin ist ein TypeScript-Package mit:
- `plugin.json` - Metadaten (name, version, description)
- Routes (API-Endpoints)
- Services (Business-Logic)
- UI-Komponenten (React-Pages)
- Sidebar-Manifest (Admin-Navigation)
- Translations (de.json, en.json)
- optional: Delivery-Action-Types, Email-Templates

## Marketplace

Siehe [Marketplace](/glossar/nexus-plattform/marketplace). Kunden installieren Plugins mit einem Klick aus dem Marketplace.

## Custom-Plugins

Entwickler koennen eigene Plugins bauen. Plugin-Development-Doku unter `docs/PLUGIN_DEVELOPMENT.md` im Nexus-Repo. Plugin-SDK ist geplant (Feature 22).

## Private Plugins

Nicht alle Plugins sind public. Einige (marketplace-provider, server-management) sind SAC-intern und nicht im Marketplace.
