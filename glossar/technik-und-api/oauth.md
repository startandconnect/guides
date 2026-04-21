---
title: OAuth 2.0
order: 4
excerpt: Per Drittanbieter einloggen ohne Passwort
---

# OAuth 2.0

Standardisierter Fluss, bei dem sich Nutzer ueber einen Drittanbieter (Google, Facebook, Microsoft, Circle) anmelden statt direkt Passwort bei dir einzugeben. Auch verwendet fuer APIs die im Namen eines Nutzers handeln.

## Der Fluss (Authorization Code Flow)

1. Dein User klickt "Mit Google anmelden"
2. Redirect zu Google mit `client_id` + Scope (was du lesen willst)
3. User loggt sich bei Google ein + autorisiert dich
4. Google redirected zurueck zu dir mit `code`
5. Du tauschst `code` gegen `access_token` + `refresh_token`
6. Mit dem Access-Token kannst du Google-APIs im Namen des Users nutzen

Der User gibt nie sein Google-Passwort bei dir ein - das ist der Vorteil.

## Access Token vs Refresh Token

- **Access Token** - kurzlebig (typisch 1 Std), wird bei jedem Request mitgesendet
- **Refresh Token** - langlebig, nur um neue Access-Tokens zu bekommen. NICHT bei Request mitsenden.

Wenn Access-Token abgelaufen: Refresh-Token → neuer Access-Token → weiter.

## Scopes

Was darfst du im Namen des Users machen. Google-Scopes z.B.:
- `userinfo.email` - Email lesen
- `calendar.readonly` - Kalender lesen
- `drive.file` - Dateien lesen/schreiben die deine App erstellt hat

Minimale Scopes = Kunde vertraut dir eher.

## OAuth in Nexus

- **Circle-Integration-Plugin** nutzt OAuth fuer Login mit Circle-Account
- **Google-Ads-Plugin** nutzt OAuth fuer Conversion-Upload
- **Google Drive Upload** im Wiki-Consistency-Worker nutzt OAuth Refresh-Token-Flow

## OpenID Connect (OIDC)

Schicht auf OAuth fuer "Wer ist dieser User?" statt nur "Was darf er?". Viele Anbieter implementieren OIDC auf OAuth.

## Sicherheit

- **PKCE** (Proof Key for Code Exchange) - zusaetzlicher Schutz fuer Public Clients (z.B. Mobile-Apps)
- **State-Parameter** - gegen CSRF-Angriffe im Redirect
- **Client-Secret** - nur Server-seitig, niemals ins Frontend

Das sind Sachen die Nexus-seitig implementiert sind und du nicht selber bauen musst.
