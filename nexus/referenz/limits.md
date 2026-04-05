---
title: Limits & Standardwerte
order: 6
excerpt: Technische Limits, Dateitypen, Rate Limits und Standardwerte in Nexus
---

# Limits & Standardwerte

Übersicht aller technischen Limits und Standardkonfigurationen in Nexus.

## Upload-Limits

| Bereich | Limit | Details |
|---|---|---|
| Upload-Größe (Bilder) | je nach Konfiguration | Standard: 10 MB |
| Upload-Größe (Dokumente) | je nach Konfiguration | Standard: 10 MB |
| Upload-Größe (Fonts) | je nach Konfiguration | Standard: 5 MB |

## Erlaubte Dateitypen

| Kategorie | Erlaubte Formate |
|---|---|
| Bilder | JPG, PNG, WebP, GIF, SVG |
| Fonts | WOFF2, WOFF |
| Dokumente | PDF, ZIP, DOC, DOCX |

## Rate Limits

| Bereich | Limit | Details |
|---|---|---|
| API Rate Limit | Konfigurierbar | Standard: keine harten Limits |
| Forms Submit | 5 pro Minute pro IP | Schutz vor Spam |
| Login-Versuche | Konfigurierbar | Brute-Force-Schutz |

## E-Mail Limits

| Anbieter | Kostenloses Kontingent | Hinweis |
|---|---|---|
| Mailgun Free | 100 E-Mails/Tag | Nur Sandbox-Domain im Free-Tier |
| Brevo Free | 300 E-Mails/Tag | Inklusive eigener Domain |
| Amazon SES | 200 E-Mails/Tag | Nur im Sandbox-Modus |

:::info[Hinweis]
Das tatsächliche E-Mail-Limit hängt von deinem SMTP-Provider und deinem Tarif ab. Nexus selbst hat kein E-Mail-Limit.
:::

## Daten & Speicher

| Bereich | Limit | Details |
|---|---|---|
| Produkte | Unbegrenzt | |
| Kunden | Unbegrenzt | |
| Bestellungen | Unbegrenzt | |
| E-Mail Templates | Unbegrenzt | |
| Blog-Beiträge | Unbegrenzt | |
| Seiten | Unbegrenzt | |
| Events | Unbegrenzt | |
| Newsletter-Abonnenten | Unbegrenzt | |

## Plugins

| Bereich | Limit | Details |
|---|---|---|
| Marketplace-Plugins | 12+ verfügbar | Wächst kontinuierlich |
| Private Plugins | Unbegrenzt | Eigene Plugins per ZIP installierbar |
| Gleichzeitig installiert | Unbegrenzt | Performance kann bei vielen Plugins variieren |

## Analytics

| Bereich | Standardwert | Details |
|---|---|---|
| Datenaufbewahrung | 90 Tage | Konfigurierbar pro Portal |
| Dashboard-Zeitraum | 30 Tage | Kann im Dashboard angepasst werden |
| Export-Format | CSV | Über Analytics-Bereich exportierbar |

## API Keys & Berechtigungen

| Bereich | Details |
|---|---|
| Anzahl API Keys | Unbegrenzt |
| Berechtigungen | Granular pro Bereich (z.B. `products:read`, `orders:write`) |
| Key-Format | Alphanumerischer String |
| Authentifizierung | `x-api-key` Header + `User-Agent` Header |

### Verfügbare API-Scopes

| Scope | Beschreibung |
|---|---|
| `products:read` | Produkte lesen |
| `products:write` | Produkte erstellen und bearbeiten |
| `orders:read` | Bestellungen lesen |
| `orders:write` | Bestellungen erstellen und bearbeiten |
| `customers:read` | Kundendaten lesen |
| `customers:write` | Kundendaten bearbeiten |
| `emails:read` | E-Mail Templates lesen |
| `emails:write` | E-Mail Templates bearbeiten |
| `events:read` | Events lesen |
| `events:write` | Events erstellen und bearbeiten |
| `analytics:read` | Analytics-Daten lesen |
| `settings:read` | Einstellungen lesen |
| `settings:write` | Einstellungen bearbeiten |

## Rollen

| Bereich | Limit | Details |
|---|---|---|
| Vordefinierte Rollen | 6 | Owner, Admin, Member, Support, Seller, Accountant |
| Custom Roles | Unbegrenzt | Eigene Rollen mit individuellen Berechtigungen |
| Teammitglieder | Unbegrenzt | |

:::tip[Tipp]
Wenn du auf ein Limit stößt, das nicht hier aufgeführt ist, ist es wahrscheinlich konfigurierbar. Prüfe die Einstellungen oder frage im Support nach.
:::
