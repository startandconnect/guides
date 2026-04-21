---
title: Multi-Tenant
order: 8
excerpt: Wie mehrere Kunden dasselbe System nutzen
---

# Multi-Tenant

Architektur bei der mehrere Kunden dasselbe Software-System nutzen, aber ihre Daten isoliert sind. Nexus ist Multi-Tenant **mit eigener Datenbank pro Kunde**.

## Drei Varianten

**Shared Database, Shared Schema**
- Alle Kunden in einer DB, unterschieden durch `tenant_id`-Spalte.
- Preiswert, aber Risiko bei Daten-Leak durch Bug.
- Typisch bei Low-Cost-SaaS.

**Shared Database, Separate Schema**
- Eine DB, jeder Kunde eigenes Schema.
- Bessere Isolation als Shared-Schema, aber noch nicht voellig.

**Separate Database** ← **Das macht Nexus**
- Jeder Kunde eigene physische Datenbank.
- Maximale Isolation. Ein Bug kann nicht Daten zwischen Kunden leaken.
- DSGVO-Konformitaet direkt gegeben.
- Hoehere Infrastruktur-Kosten, dafuer starker Wettbewerbsvorteil.

## Konsequenzen fuer Entwicklung

**Schema-Migrationen muessen idempotent sein.** Wenn du eine neue Spalte hinzufuegst, laeuft diese Migration auf jeder Kunden-DB einzeln. Bei 50 Kunden = 50 Schema-Updates.

Deshalb bei Nexus:
- `ADD COLUMN IF NOT EXISTS`
- `DO $$ EXCEPTION WHEN duplicate_column THEN NULL; END $$;`
- Keine destructive Migrations ohne Backup

## Konsequenzen fuer Backup

Jede Instance hat ihren eigenen Backup-Rhythmus. Nightly-Backup-Scripts auf Dokploy. Restore betrifft nur eine Instance, nicht alle.

## Konsequenzen fuer Features

Features, die nur ein Kunde braucht, werden ueber das [Plugin-System](/glossar/nexus-plattform/plugin) geloest - nicht im Core eingebaut. Core-Aenderungen muessen fuer alle passen.

## Kunden-spezifische Einstellungen

Jede Instance hat ihre eigene `Setting`-Tabelle. Branding, Payment-Config, Mail-Templates - alles per Instance konfigurierbar.

## Kosten-Modell

Pro Kunde ~5 Euro Infrastruktur-Kosten (kleiner Container + kleine DB). Pro Server (Hetzner HC-Series) ca. 50 Kunden. Scaling: mehr Server = mehr Kunden, lineares Kosten-Wachstum.
