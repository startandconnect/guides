---
title: Fehlerbehebung
order: 4
excerpt: Häufige Probleme und Lösungen - Stripe, E-Mail, Checkout, Login, API und mehr
---

# Fehlerbehebung

Hier findest du Lösungen für die häufigsten Probleme in Nexus. Jedes Problem ist mit Symptom, möglicher Ursache und Lösung beschrieben.

## 1. Stripe Webhook funktioniert nicht

**Symptom:** Bestellungen bleiben auf `PENDING`, obwohl der Kunde bezahlt hat. Im Stripe Dashboard ist die Zahlung erfolgreich.

**Mögliche Ursachen:**

| Ursache | Prüfung | Lösung |
|---|---|---|
| Webhook-URL falsch | Stripe Dashboard > Webhooks > Endpoint prüfen | URL muss auf `/api/stripe/webhook` enden |
| Signing Secret falsch | In den Nexus-Einstellungen prüfen | Secret aus Stripe Dashboard kopieren und neu eintragen |
| Webhook nicht aktiv | Stripe Dashboard > Webhooks > Status | Endpoint aktivieren |
| Falscher Modus (Test/Live) | Stripe Dashboard > Test/Live-Toggle | Sicherstellen, dass Webhook im richtigen Modus angelegt ist |

**So prüfst du die Webhook-Logs:**

1. Gehe in dein Stripe Dashboard zu **Entwickler > Webhooks**
2. Klicke auf den Endpoint
3. Unter **Versuche** siehst du alle gesendeten Events mit Statuscode
4. Ein `200`-Statuscode bedeutet Erfolg, alles andere ist ein Fehler

:::warning[Wichtig]
Test-Webhooks und Live-Webhooks sind getrennt. Wenn du vom Testmodus in den Live-Modus wechselst, musst du einen neuen Webhook-Endpoint mit dem Live-Signing-Secret anlegen.
:::

## 2. E-Mail kommt nicht an

**Symptom:** Kunden erhalten keine Bestellbestätigungen, Passwort-Reset-Mails oder andere System-E-Mails.

| Ursache | Prüfung | Lösung |
|---|---|---|
| SMTP nicht konfiguriert | Einstellungen > E-Mail | SMTP-Zugangsdaten eintragen |
| SMTP-Zugangsdaten falsch | Test-Mail senden | Zugangsdaten beim Provider prüfen |
| E-Mail im Spam-Ordner | Spam-Ordner des Empfängers prüfen | SPF, DKIM und DMARC konfigurieren |
| Provider-Limit erreicht | Logs beim SMTP-Provider prüfen | Auf höheres Kontingent upgraden |
| Absender-Domain nicht verifiziert | Provider-Dashboard prüfen | Domain beim SMTP-Provider verifizieren |

**E-Mail Log prüfen:**

Unter **E-Mails > Log** siehst du alle versendeten E-Mails mit Status. Fehlgeschlagene Zustellungen werden mit Fehlerdetails angezeigt.

:::tip[Tipp]
Sende immer zuerst eine Test-Mail an dich selbst, bevor du SMTP-Änderungen speicherst. So siehst du sofort, ob die Konfiguration funktioniert.
:::

## 3. Checkout zeigt Fehler

**Symptom:** Kunden sehen eine Fehlermeldung beim Checkout oder die Bezahlung schlägt fehl.

| Ursache | Prüfung | Lösung |
|---|---|---|
| Stripe Keys (Test vs Live) | Einstellungen > Zahlung | Sicherstellen, dass die richtigen Keys (Test oder Live) eingetragen sind |
| Produkt nicht aktiv | Produkt-Status prüfen | Produkt auf `ACTIVE` setzen |
| Kein Preis hinterlegt | Produkt bearbeiten > Preise | Mindestens einen Preis anlegen |
| Stripe-Konto nicht vollständig | Stripe Dashboard | Onboarding im Stripe Dashboard abschließen |
| Währung nicht unterstützt | Stripe Dashboard > Einstellungen | Gewünschte Währung in Stripe aktivieren |

## 4. Seite wird nicht angezeigt

**Symptom:** Eine Seite im Portal zeigt einen 404-Fehler oder ist leer.

| Ursache | Prüfung | Lösung |
|---|---|---|
| Seite nicht veröffentlicht | Seiten-Status prüfen | Status auf `PUBLISHED` setzen |
| Slug falsch | URL und Slug vergleichen | Slug in den Seiteneinstellungen korrigieren |
| Cache veraltet | - | Cache leeren (Browser und ggf. CDN) |
| Seite gelöscht | Papierkorb prüfen | Seite wiederherstellen oder neu anlegen |

## 5. Login funktioniert nicht

**Symptom:** Nutzer können sich nicht einloggen, obwohl die Zugangsdaten korrekt sind.

| Ursache | Prüfung | Lösung |
|---|---|---|
| Falsches Passwort | - | Passwort über "Passwort vergessen" zurücksetzen |
| Cookies blockiert | Browser-Einstellungen | Cookies für die Portal-Domain erlauben |
| Browser-Cache | - | Cache und Cookies löschen, Browser neu starten |
| Account deaktiviert | Admin-Dashboard > Kunden | Account-Status prüfen und ggf. reaktivieren |

## 6. API Key wird abgelehnt

**Symptom:** API-Anfragen geben einen `401 Unauthorized` oder `403 Forbidden` zurück.

| Ursache | Prüfung | Lösung |
|---|---|---|
| Key nicht aktiv | Einstellungen > API Keys | Prüfen, ob der Key aktiv ist |
| Falsche Berechtigungen | Key-Details prüfen | Benötigte Scopes (z.B. `products:read`) hinzufügen |
| User-Agent fehlt | Request-Header prüfen | `User-Agent` Header im Request setzen |
| Key falsch kopiert | Key erneut kopieren | Sicherstellen, dass keine Leerzeichen im Key sind |

:::info[Hinweis]
API Keys werden als `x-api-key` Header gesendet. Stelle sicher, dass du den Header korrekt setzt: `x-api-key: dein-api-key`.
:::

## 7. Plugin lässt sich nicht installieren

**Symptom:** Beim Hochladen eines Plugins erscheint eine Fehlermeldung.

| Ursache | Prüfung | Lösung |
|---|---|---|
| Version nicht kompatibel | Plugin-Dokumentation prüfen | Plugin-Version passend zur Nexus-Version verwenden |
| ZIP-Format ungültig | Dateistruktur prüfen | Plugin muss als gültige ZIP-Datei mit korrekter Ordnerstruktur vorliegen |
| Plugin bereits installiert | Plugin-Liste prüfen | Vorhandenes Plugin erst deinstallieren, dann neu installieren |
| Dateigröße zu groß | Upload-Limit prüfen | Upload-Limit in den Einstellungen anpassen |

## 8. Newsletter DOI-Mail kommt nicht

**Symptom:** Nach der Newsletter-Anmeldung erhält der Abonnent keine Double-Opt-In-Bestätigungsmail.

| Ursache | Prüfung | Lösung |
|---|---|---|
| SMTP nicht konfiguriert | Einstellungen > E-Mail | SMTP-Zugangsdaten eintragen und testen |
| DOI-Template fehlt | E-Mail Templates prüfen | DOI-Template erstellen oder Standard wiederherstellen |
| Auf Suppression List | E-Mail Logs prüfen | E-Mail-Adresse von der Suppression List entfernen |
| E-Mail bereits bestätigt | Abonnenten-Liste prüfen | Abonnent ist bereits bestätigt, keine erneute DOI nötig |

## 9. Event-Registrierung schlägt fehl

**Symptom:** Teilnehmer können sich nicht für ein Event registrieren.

| Ursache | Prüfung | Lösung |
|---|---|---|
| Kapazität erreicht | Event-Details > Teilnehmer | Kapazität erhöhen oder Warteliste aktivieren |
| Event nicht aktiv | Event-Status prüfen | Event auf `PUBLISHED` oder `ACTIVE` setzen |
| Registrierung geschlossen | Registrierungszeitraum prüfen | Anmeldefrist verlängern |
| Event bereits vorbei | Event-Datum prüfen | Neues Event-Datum setzen oder neues Event erstellen |

## 10. Bilder werden nicht angezeigt

**Symptom:** Hochgeladene Bilder erscheinen nicht auf der Seite oder im Blog.

| Ursache | Prüfung | Lösung |
|---|---|---|
| Upload fehlgeschlagen | Media Library prüfen | Bild erneut hochladen |
| Dateigröße zu groß | Upload-Limit prüfen | Bild komprimieren oder Upload-Limit anpassen |
| Falsches Dateiformat | Dateiendung prüfen | Unterstützte Formate: JPG, PNG, WebP, GIF, SVG |
| Pfad geändert | Bild-URL prüfen | Bild neu einbinden oder URL aktualisieren |
| CDN-Cache veraltet | - | CDN-Cache leeren oder einige Minuten warten |

:::tip[Tipp]
Komprimiere Bilder vor dem Upload mit Tools wie TinyPNG oder Squoosh. Das verbessert die Ladezeit und vermeidet Upload-Probleme.
:::
