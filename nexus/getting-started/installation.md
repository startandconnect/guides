---
title: Installation
order: 1
excerpt: Nexus installieren und einrichten
---

# Installation

Nexus wird als Managed Service bereitgestellt. Du brauchst nichts lokal zu installieren.

## Zugang erhalten

1. Gehe zu deiner Nexus-URL (z.B. `portal.deinefirma.de`)
2. Klicke auf "Registrieren"
3. Fulle das Formular aus
4. Bestaetige deine E-Mail-Adresse

:::tip[Tipp]
Falls du eine Einladung per E-Mail erhalten hast, klicke einfach auf den Link in der Mail. Dein Account wird automatisch erstellt.
:::

## Erste Anmeldung

Nach der Registrierung kannst du dich sofort anmelden. Du landest auf dem Dashboard, wo du einen Ueberblick ueber dein Portal hast.

```bash
# Falls du die API nutzen moechtest:
curl -X POST https://portal.deinefirma.de/api/auth/login \
  -H "Content-Type: application/json" \
  -d '{"email": "deine@email.de", "password": "dein-passwort"}'
```

## System-Anforderungen

Nexus laeuft vollstaendig in der Cloud. Alles was du brauchst:

| Anforderung | Minimum |
|-------------|---------|
| Browser | Chrome, Firefox, Safari (aktuell) |
| Internet | Stabile Verbindung |
| Bildschirm | Min. 1024px Breite |

