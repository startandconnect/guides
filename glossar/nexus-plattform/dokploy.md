---
title: Dokploy
order: 17
excerpt: Das Deployment-Tool im Hintergrund
---

# Dokploy

Das Deployment- und Container-Management-Tool, das Nexus-Instances automatisch deployt und verwaltet. Laeuft bei SAC auf einem eigenen Hetzner-Server, verwaltet alle Kunden-Container.

## Was Dokploy macht

- **Container-Orchestrierung** - Docker-Compose auf Steroiden
- **Auto-Deploy** aus Docker-Image-Updates
- **SSL-Zertifikate** via Let's Encrypt automatisch
- **Reverse-Proxy** (Traefik) fuer Routing
- **Backups** nightly, pro Container
- **Logs-Aggregation** pro Container einsehbar

## Warum nicht Kubernetes

Dokploy ist leichtgewichtiger. Fuer 50-200 Container ausreichend, deutlich einfacher zu betreiben als K8s. Wenn wir 1000+ Container waeren, wuerden wir wahrscheinlich wechseln.

## Wie Nexus mit Dokploy interagiert

**Admin (SAC):**
- Deploy-Script `deploy-nexus dev|provider|latest` pusht neues Docker-Image
- Dokploy-API triggert Redeploy pro Container
- Container zieht neues Image, startet neu

**Customer-Instance:**
- Container laueft autonom
- Pull neues Image beim naechsten Redeploy (manuell oder auto)
- Restart ohne Downtime dank Rolling-Deploy

## Redeploy-Trigger

`POST http://91.98.132.56:3000/api/compose.deploy` mit `composeId` als Body. Jede Compose-Definition entspricht einer Nexus-Instance.

Nexus-Plugin `server-management` nutzt diese API zum Provisioning neuer Kunden-Instances.

## Container-Regeln

**Niemals `docker compose up/down` direkt auf dem Host.** Container muessen immer ueber Dokploy redeployed werden - manueller `docker compose` erzeugt Container mit falschem Projekt-Prefix und verbindet sich mit falschen Volumes.

Details im Wiki unter `products/nexus/deployment.md`.

## Scaling

Pro Server ca. 50 Container (je nach Last). Wenn ein Server voll: neuen Server bereitstellen, Dokploy dort installieren, weitere Instances darauf. Cross-Server-Deployment ist noch nicht automatisiert (manuelles Setup).

## Backup-Strategie

- **Vor jedem Provider-Deploy**: Manuelles DB-Backup via Dokploy
- **Nightly automatisch**: alle Kunden-Instances
- **Volumes bleiben** auch bei Container-Redeploy erhalten (wichtig fuer Plugin-Updates, siehe `feedback_plugin_deploy.md`)
