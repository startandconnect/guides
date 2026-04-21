---
title: Instance
order: 2
excerpt: Deine eigene Nexus-Umgebung
---

# Instance (Instanz)

Deine eigene, isolierte Nexus-Umgebung. Jede Instance hat ihre eigene Subdomain, Datenbank, Konfiguration und Plugin-Auswahl.

## Was eine Instance umfasst

- **Docker-Container** mit der Nexus-Software (API + Web)
- **Eigene PostgreSQL-Datenbank** (physisch separate Datenbank, nicht nur Schema)
- **Eigene Subdomain** (z.B. `deinshop.nexus.sac.run` oder deine eigene Custom-Domain)
- **Eigene Media-Files** (Bilder, PDFs) in separatem Volume
- **Eigener Admin-Zugang** mit eigenem OWNER-Account

## Isolation

Ein Kunde kann die Daten eines anderen Kunden nicht sehen - weder durch API-Bugs noch durch DB-Abfragen. Die physische Trennung der Datenbanken macht Datenleaks technisch unmoeglich.

## Betrieb

Alle Instances laufen auf Hetzner-Servern in Deutschland, verwaltet durch [Dokploy](/glossar/nexus-plattform/dokploy). Typisch 50 Instances pro Server, abhaengig von Traffic.

## Setup-Prozess

Neue Instance wird via Provisioning-Pipeline angelegt:
1. Dokploy-App erstellen
2. Datenbank initialisieren
3. Env-Variablen setzen
4. Erste Migration laufen
5. Admin-Account erzeugen
6. Marketplace-Verbindung konfigurieren

Dauert etwa 5 Minuten fuer die Provisionierung.

## Updates

Nexus-Updates werden zentral gebaut (deploy-nexus-Skript):
- **dev** - interne Testinstanz (dev-nexus.s2.sac.run)
- **provider** - startandconnect.com
- **latest** - alle Kunden-Instances (via Docker-Image-Tag)

Kunden-Instances pullen das Latest-Image beim naechsten Redeploy.

## Plugins pro Instance

Jede Instance entscheidet selbst welche Plugins aktiv sind. Die Marketplace-Verbindung zeigt verfuegbare Plugins an, Admin installiert mit einem Klick.

## Kunden-Domain

Standard: `<slug>.nexus.sac.run`. Upgrade auf eigene Domain: CNAME setzen, DNS warten, Nexus erzeugt automatisch Let's-Encrypt-Zertifikat.

## Beispiel-Instances

- `startandconnect.com` (SAC selbst)
- `events.smileupyourlife.de` (SUYL / Kathi Wengert)
