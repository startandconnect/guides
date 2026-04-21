---
title: CORS und CSRF
order: 11
excerpt: Zwei wichtige Browser-Sicherheits-Mechanismen
---

# CORS und CSRF

Oft verwechselt. Beides Browser-Security-Themen, aber ganz verschiedene Probleme.

## CORS (Cross-Origin Resource Sharing)

Regelt, ob dein Browser einen API-Call zu einer anderen Domain machen darf. Default: **nein**, du kannst nur zu deiner eigenen Domain.

**Problem:** Dein React-Frontend auf `app.example.com` will API-Calls zu `api.example.com` machen. Browser blockiert das per Same-Origin-Policy.

**Loesung:** Der API-Server sendet bei jedem Response einen Header `Access-Control-Allow-Origin: https://app.example.com`. Browser sieht: "Ok, die API erlaubt Calls von app". Request durch.

Nexus konfiguriert CORS automatisch fuer die Portal-Domain.

## CSRF (Cross-Site Request Forgery)

Boesartige Website versucht, im Namen des eingeloggten Nutzers Requests an einen Dienst zu stellen.

**Szenario:** Du bist bei `deinshop.com` eingeloggt. Eine andere boese Website zeigt dir ein Bild, aber der Image-Src ist `https://deinshop.com/api/delete-account`. Browser sendet Cookie automatisch mit, dein Account ist weg.

**Schutz:**

1. **SameSite-Cookies** - moderne Browser senden Cookies mit `SameSite=Lax` oder `Strict` nicht automatisch bei Cross-Site-Requests
2. **CSRF-Tokens** - jeder State-aendernde Request braucht einen Token den der Server nur deinem Frontend gibt
3. **Origin/Referer-Check** - Server prueft, ob der Request von der erwarteten Seite kommt

Nexus nutzt SameSite-Cookies + Origin-Check.

## Verwechslung vermeiden

- **CORS** - **welche Domains** duerfen auf deine API zugreifen (Integration-Thema)
- **CSRF** - **wer hat** den Request ausgeloest (Security-Thema)

Beides nebeneinander wichtig.

## Wenn APIs nicht im Browser sind

Server-zu-Server API-Calls (z.B. dein Backend ruft Nexus-API) sind von CORS und CSRF NICHT betroffen. Beides ist Browser-spezifisch.
