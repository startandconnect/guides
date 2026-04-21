---
title: Änderungshistorie (Audit Log)
order: 12
excerpt: Nachvollziehen wer wann was geändert hat - lückenlose Änderungshistorie für alle wichtigen Daten
---

# Änderungshistorie

Nexus protokolliert automatisch alle wichtigen Änderungen in deinem Account. Du kannst jederzeit nachvollziehen wer was wann geändert hat.

## Wo du die Änderungshistorie findest

### Pro Datensatz (Detail-Seite)

Für diese Bereiche gibt es einen "Änderungshistorie"-Tab direkt beim jeweiligen Datensatz:

- **Bestellungen** → Bestellung öffnen → Tab "Änderungshistorie"
- **Produkte** → Produkt öffnen → Tab "Änderungshistorie"
- **Kunden** → Kontakt öffnen → Tab "Änderungshistorie"
- **Deals** → Deal öffnen → Karte "Änderungshistorie" am Seitenende
- **Rechnungen** → Rechnung öffnen → Tab "Änderungshistorie"
- **Abonnements** → Abo öffnen → Tab "Änderungshistorie"
- **Gutscheine** → Gutschein öffnen → Tab "Änderungshistorie"
- **Seiten** → Seite öffnen → Tab "Änderungshistorie"
- **Blog-Posts** → Post öffnen → Tab "Änderungshistorie"
- **Events** → Event öffnen → Tab "Änderungshistorie"
- **Formulare** → Formular öffnen → Tab "Änderungshistorie"

### Systemweites Log

Unter **Einstellungen → System → Logs → Änderungen** findest du alle Änderungen über alle Bereiche hinweg.

## Was wird protokolliert

Für jeden Eintrag siehst du:

| Information | Bedeutung |
|---|---|
| **Zeitpunkt** | Wann die Änderung stattfand |
| **Aktion** | Was passiert ist (erstellt, geändert, gelöscht) |
| **Benutzer** | Wer die Änderung vorgenommen hat (oder "System" für automatische Aktionen) |
| **Quelle** | Ob die Änderung manuell oder durch einen automatischen Prozess ausgelöst wurde |
| **Geänderte Felder** | Welche Felder sich von welchem zu welchem Wert verändert haben |

## Filter und Suche

Im systemweiten Log kannst du filtern nach:

- **Quelle:** Manuell (durch Benutzer) oder automatisch (Middleware)
- **Bereich:** z.B. nur Bestellungen oder nur Produkte
- **Zeitraum:** Datum-Bereich eingrenzen

## Typische Anwendungsfälle

**Kundenanfrage bearbeiten:** "Wann wurde mein Abo storniert?" - im Abo-Tab "Änderungshistorie" siehst du den genauen Zeitpunkt und ob es manuell oder automatisch passierte.

**Team-Transparenz:** Wenn mehrere Personen im Dashboard arbeiten, siehst du wer welche Produkte oder Preise angepasst hat.

**Fehler-Nachverfolgung:** Wenn Daten unerwartet geändert wurden, lässt sich der Zeitpunkt und Auslöser schnell eingrenzen.

**Compliance:** Die Änderungshistorie wird 10 Jahre aufbewahrt (konfigurierbar unter Einstellungen → System).

## Hinweise

- Automatische System-Aktionen (z.B. Stripe-Webhook-Updates, Cron-Jobs) erscheinen mit der Quelle "System"
- Login-Ereignisse werden nicht in der Änderungshistorie, sondern im separaten Sicherheits-Log festgehalten
- Gelöschte Datensätze bleiben im Log erhalten (der Eintrag zeigt "gelöscht")
