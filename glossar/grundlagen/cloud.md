---
title: Cloud
order: 3
excerpt: Wenn deine Daten nicht auf deinem Rechner liegen
---

# Cloud

"Der Cloud" ist einfach: Server die woanders stehen. Statt dass du deine Daten auf deiner Festplatte oder eurem Buero-Server hast, liegen sie in einem Rechenzentrum. Du erreichst sie ueber das Internet.

## Public Cloud vs Private Cloud

- **Public Cloud**: Geteilte Infrastruktur fuer viele Kunden (AWS, Google Cloud, Azure, Hetzner Cloud). Guenstig, flexibel, skalierbar.
- **Private Cloud**: Eigene Infrastruktur nur fuer deine Firma. Teurer, aber mehr Kontrolle.

## Cloud-Native

Software, die direkt fuer den Betrieb in der Cloud designed wurde. Kann dynamisch skalieren, ueberlebt Server-Ausfaelle, nutzt verteilte Datenbanken. Nexus ist Cloud-Native.

## Datensouveranitaet

Die Frage wo deine Daten physisch liegen und welches Recht gilt. US-Cloud-Anbieter (AWS, Google) unterliegen dem CLOUD Act - US-Behoerden koennen theoretisch Zugriff verlangen. Europa-Cloud (Hetzner in Deutschland) nicht.

Nexus haltet deine Daten in Deutschland. Relevant fuer [DSGVO](/glossar/recht-und-dsgvo/dsgvo) und Kunden-Vertrauen.

## Redundanz

Mehrere Kopien deiner Daten auf verschiedenen Servern. Wenn ein Server ausfaellt, bist du trotzdem online. Cloud-Anbieter machen das automatisch.

## Verfuegbarkeit (Uptime)

Wie oft ein Dienst erreichbar ist. 99,9 Prozent Uptime = maximal 8,7 Stunden Ausfall pro Jahr. 99,99 Prozent = 52 Minuten. SLAs (Service Level Agreements) garantieren bestimmte Werte.
