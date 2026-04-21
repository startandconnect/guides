---
title: Server-Standort
order: 11
excerpt: Wo deine Daten physisch liegen
---

# Server-Standort

Wo deine Daten und die deiner Kunden physisch gespeichert werden. Hat direkte Auswirkung auf DSGVO-Konformitaet und Vertrauen.

## EU-Server vs USA-Server

**EU (vor allem Deutschland)**
- Unterliegen deutschem/europaeischem Recht
- DSGVO gilt direkt
- Keine US-Behoerden-Zugriff
- Faellt meist einfacher unter "bewaehrte Standards"

**USA**
- CLOUD-Act: US-Behoerden koennen Zugriff verlangen, auch wenn Daten physisch im Ausland liegen
- Schrems-II-Urteil: US-Datentransfers brauchen spezielle Absicherungen
- Standard Contractual Clauses + Zusatz-Massnahmen noetig

## Nexus

Alle Nexus-Instanzen laufen auf **Hetzner in Deutschland** (Nuernberg, Falkenstein). Keine USA-Uebertragung.

Ausnahme: Wenn du Services integrierst die in USA hosten:
- Stripe (hat EU-Subsidiary mit Datenverarbeitung teilweise in US)
- Google Analytics (wird durch Cookie-Consent abgedeckt)
- OpenAI (wenn Chatbot-Plugin aktiv)

Diese muessen in deiner Datenschutzerklaerung aufgefuehrt werden.

## Relevanz fuer B2B-Kunden

Grosse Unternehmen fragen oft explizit nach EU-Hosting. Fuer Agenturen und Coaches die grosse Firmen als Kunden haben: Nexus-Server-Standort in Deutschland ist Verkaufsargument.

## Hetzner speziell

- **Zertifiziert** (ISO 27001)
- **AV-Vertrag** standardisiert
- **Frankfurt-Standort** gilt als sehr zuverlaessig
- **Preiswert** im Vergleich zu AWS/Azure EU

## Was passiert bei Ausfall Hetzner

Hypothetisch: Hetzner-Rechenzentrum faellt aus fuer laengere Zeit.
- Nexus-Instances haben tagesaktuelle Backups
- Failover zu anderem Hetzner-Standort moeglich
- Disaster-Recovery-Plan in SAC-Runbooks

Nie passiert bisher. Die zwei groessten Hetzner-Standorte sind geo-redundant.

## Server-Standort auf Website kommunizieren

Best Practice:
- In Datenschutzerklaerung explizit erwaehnen
- Im Footer oder About-Seite als Trust-Signal
- Bei B2B-Proposals aktiv hervorheben

SAC-Website hat "Server in Deutschland" als Trust-Element.

## Ausnahme: Kunden-eigenes Hosting

Wenn ein grosser Kunde sagt "das System muss bei uns laufen": moeglich als Custom-Deployment. Kostet extra, aber machbar. Nexus-Architektur ist portabel.

## EU-eigener vs Hetzner-Dedicated

- **Shared VPS bei Hetzner** (Nexus-Standard): preiswert, vollkommen okay fuer DSGVO
- **Dedicated Server**: hoehere Kosten, keine Nachbarn auf gleicher Hardware, vielleicht fuer Enterprise-Kunden relevant
- **Eigene Infrastruktur** (On-Premise): nur wenn der Kunde das unbedingt will - selten, teuer, wartungsintensiv
