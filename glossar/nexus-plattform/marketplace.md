---
title: Marketplace
order: 4
excerpt: Wo du Plugins installierst
---

# Marketplace

Das Plugin-Verzeichnis fuer deine Nexus-Instance. Ueber den Marketplace findest du alle verfuegbaren Plugins und installierst sie mit einem Klick.

## Wo finden

Im Admin unter `/manage/plugins/marketplace`. Zeigt:
- Aktive Plugins (schon installiert)
- Verfuegbare Plugins (zur Installation bereit)
- Update-Status (wenn neue Version im Marketplace)

## Installation

1. Plugin auswaehlen
2. "Installieren" klicken
3. Plugin-ZIP wird von SAC-Marketplace-Server geladen
4. Container laedt das Plugin neu
5. Nach wenigen Sekunden ist das Plugin aktiv

Kein Server-Restart noetig, Plugin-Code wird dynamisch geladen.

## Updates

Plugin-Updates werden:
- **Automatisch** beim Container-Redeploy (pull neues Image)
- **Manuell** via Marketplace-UI ("Update-Button")

**Caveat:** Nach `deploy-nexus` sind Plugins auf existierenden Kunden-Instances nicht automatisch aktualisiert. Volume ueberlebt Redeploy. Admin muss manuell updaten (siehe `wiki/reference/feedback_plugin_deploy.md`).

## Updates publishen (fuer SAC)

Plugin-Bumpen:
1. Code aendern in `plugins-private/<plugin>/`
2. `plugin.json` Version hochbumpen
3. Deploy-Skript baut ZIP
4. ZIP wird auf Marketplace-Server gepusht
5. Alle Instances sehen beim naechsten Fetch die neue Version

## Marketplace-Provider

Interner Plugin das den Marketplace betreibt. Lebt nur in der SAC-Master-Instance. Andere Instances verbinden sich dorthin via Plugin-Catalog-Service.

## Private Plugins

Nicht jedes Plugin gehoert in den Marketplace. Einige sind:
- **SAC-intern** (marketplace-provider, server-management)
- **Kunden-spezifisch** (z.B. custom Plugin fuer SUYL)

Die werden direkt in die Plugin-Folder der jeweiligen Instance deployed, ohne Marketplace-Sync.

## Kosten

Plugins sind aktuell in der Nexus-Subscription enthalten. Zukuenftig kommen Third-Party-Plugins von externen Entwicklern, moeglicherweise mit eigenen Preisen (Marketplace-Commission-Modell geplant).
