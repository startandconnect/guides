---
title: Scope-Matrix
order: 16
excerpt: Das Admin-Interface fuer Rollen und Berechtigungen
---

# Scope-Matrix

Admin-UI unter `/settings/access/roles`, in der du pro Rolle x Resource x Aktion den [Scope](/glossar/nexus-plattform/scope) einstellst.

## Wie es aussieht

Eine grosse Tabelle:
- **Zeilen** - Resources (Order, Product, Customer, Invoice, ...)
- **Spalten** - Aktionen (read, create, update, delete, share)
- Pro Zelle: Scope-Dropdown (all / team / own / none)

Du klickst auf eine Zelle, aenderst den Scope, speicherst - greift sofort.

## Rollen-Switcher

Oben ein Dropdown fuer die Rolle die du konfigurieren willst: OWNER, ADMIN, MEMBER, SELLER, SUPPORT, ACCOUNTANT, CUSTOMER. Plus Custom-Rollen wenn angelegt.

Klickst du eine andere Rolle, zeigt sich deren Matrix. Defaults kommen aus Code, Overrides aus `RoleScopeOverride`-Tabelle.

## Visual-Cues

- **Primary Ring** (Blau) - Override ist aktiv (weicht vom Code-Default ab)
- **Orange Ring** - ungespeicherte Aenderung
- **Gelbes ⚠** - Coverage-Warnung: scope ist gesetzt, aber kein funktionierender Row-Level-Filter existiert. Siehe [Scope Coverage-Warnungen](/glossar/nexus-plattform/scope).

## Reset

Pro Rolle ein "Auf Defaults zuruecksetzen"-Button. Loescht alle Overrides fuer diese Rolle, Standard gilt wieder.

## Audit-Log-Integration

Aenderungen an der Scope-Matrix sind im Audit-Log erfasst. Wichtig fuer "wer hat SUPPORT-Rolle mehr Rechte gegeben".

## Technisch

Unter der Haube:
- `RoleScopeOverride`-Tabelle in DB
- In-Memory-Cache fuer Hot-Path-Performance
- Scope-Filter-Prisma-Extension injiziert WHERE-Clauses basierend auf Scope

Admin-UI ist nur das Interface. Die Arbeit passiert in der Prisma-Layer.

## Best Practices

- **Default-Deny** - zu breite Scopes sind ein Security-Risiko. Lieber `none` starten und gezielt oeffnen.
- **Test mit einem Test-User** - lege einen Test-User mit der Rolle an, logg dich ein, pruefe ob er nur das sieht was er soll.
- **Dokumentieren** - in `wiki/products/nexus/permissions-architecture.md` festgehalten welche Entscheidungen warum.
