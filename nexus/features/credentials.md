---
title: Credentials
order: 5
excerpt: Auth-Daten fuer externe HTTP-Calls und Webhooks zentral und verschluesselt verwalten
---

# Credentials

Credentials sind verschluesselt gespeicherte Zugangsdaten, die du in Automations-Actions wie `HTTP_REQUEST` oder `WEBHOOK` nutzt, um dich gegenueber externen Diensten zu authentifizieren. Statt Token oder Passwoerter direkt in jede Action zu schreiben, hinterlegst du sie einmal als Credential und referenzierst sie aus mehreren Rules.

Du verwaltest sie unter **Einstellungen > Automations > Credentials**.

## Wann brauchst du Credentials

Du brauchst keine Credential, wenn die externe URL keine Authentifizierung verlangt. Sobald aber:

- ein API-Key gefordert wird,
- ein Bearer-Token gesendet werden soll,
- Basic-Auth noetig ist,
- ein OAuth2-Flow vorgeschaltet ist,
- eine SMTP-Verbindung mit Login eingerichtet werden muss,

solltest du ein Credential anlegen. Vorteil: das Geheimnis steht nur einmal im System, du kannst es zentral aktualisieren, Tests laufen einheitlich und ein Audit-Log dokumentiert die Nutzung.

## Verfuegbare Typen

Es gibt sieben Core-Typen, die direkt in Nexus enthalten sind:

| Typ | Wofuer |
|---|---|
| **HTTP_HEADER_AUTH** | Beliebiger Header-Name + Wert (z.B. `X-Api-Key: ...`) |
| **BEARER_TOKEN** | Setzt `Authorization: Bearer <token>` automatisch |
| **BASIC_AUTH** | Username und Passwort, base64-codiert als Basic-Auth-Header |
| **API_KEY** | API-Key als Query-Parameter oder Header (konfigurierbar) |
| **OAUTH2_GENERIC** | OAuth2 Client-Credentials- oder Authorization-Code-Flow |
| **SMTP_CUSTOM** | SMTP-Login fuer eigene Mail-Versand-Action |
| **GENERIC_JSON** | Frei strukturierter JSON-Payload, falls keiner der Typen passt |

Plugins koennen zusaetzlich eigene Typen registrieren (z.B. ein Slack-Plugin bringt einen `SLACK_BOT_TOKEN`-Typ mit). Diese erscheinen automatisch in der Auswahl.

## Credential anlegen

1. Gehe zu **Einstellungen > Automations > Credentials**
2. Klicke auf **Neues Credential**
3. Waehle einen **Typ** aus der Liste
4. Vergib einen **Namen** (z.B. "Stripe Test Bearer", "Mailchimp API")
5. Trage die **Felder** des Typs aus (z.B. `token` fuer BEARER_TOKEN)
6. Optional: **Test-Endpoint** hinterlegen (URL fuer Test-Connection)
7. **Sichtbarkeit** waehlen: Team oder Privat (siehe unten)
8. Speichern

Nach dem Speichern siehst du nur noch die Metadaten (Name, Typ, Erstelldatum). Den eigentlichen Wert siehst auch du selbst nie wieder - er ist nur intern fuer Actions verfuegbar.

## Test-Connection

Wenn du eine Test-URL hinterlegt hast, kannst du im Detail-Dialog auf **Verbindung testen** klicken. Nexus baut den Auth-Header aus dem Credential und macht einen GET-Request gegen die URL. Du siehst:

- HTTP-Status-Code
- Antwortzeit
- Response-Body (gekuerzt)

So findest du falsch hinterlegte Tokens, bevor sie in einer scharfen Automation fehlschlagen.

::: tip[Tipp]
Du kannst die Test-URL pro Aufruf ueberschreiben, falls dein Provider mehrere Endpoints anbietet (z.B. `/me` zum Ping vs. `/users` fuer den Echtbetrieb).
:::

## Sichtbarkeit: Team vs. Privat

Beim Anlegen entscheidest du:

- **Team-Scope**: alle Team-Mitglieder mit Zugriff auf Einstellungen koennen das Credential in Actions referenzieren. Empfohlen fuer geteilte Integrationen wie eine zentrale Slack-Webhook oder die Firmen-Mailgun.
- **Privat-Scope (USER)**: nur du selbst siehst das Credential. Nuetzlich fuer Test-Tokens oder persoenliche Tools.

Den Scope kannst du nach dem Anlegen nicht mehr aendern. Wenn du einen Wechsel brauchst, lege das Credential neu an und archiviere das alte.

## Credentials in Actions nutzen

In **HTTP_REQUEST** oder **WEBHOOK**-Actions findest du im Visual Builder ein Feld **Credential**. Waehle dort eines aus der Liste der passenden Typen aus. Im JSON-Editor referenzierst du das Credential ueber sein `id`-Feld:

```json
{
  "type": "HTTP_REQUEST",
  "url": "https://api.example.com/contacts",
  "method": "POST",
  "credentialId": "cred_abc123",
  "body": {
    "email": "{{customer.email}}"
  }
}
```

Nexus baut den passenden Auth-Header aus dem Credential und sendet den Request. Bei `OAUTH2_GENERIC` mit Auto-Refresh werden abgelaufene Access-Tokens automatisch erneuert.

## Sicherheit

Credentials werden mit einer Drei-Schichten-Verschluesselung geschuetzt:

1. Eine **Master-Encryption-Key (MEK)** liegt als Datei im Volume der Instanz, nicht in der Datenbank. Auch ein vollstaendiger DB-Dump alleine reicht nicht zum Entschluesseln.
2. Eine **Data-Encryption-Key (DEK)** liegt in der DB, ist aber selbst mit dem MEK verschluesselt.
3. Jeder Credential-Wert wird mit dem DEK per AES-256-GCM verschluesselt, mit eigenem IV pro Datensatz.

Praktische Konsequenzen fuer dich:

- Werte verlassen die API niemals im Klartext, weder ans UI noch an MCP-Klienten
- Der Wert wird beim Anlegen einmal gelesen, danach kannst du ihn nur noch durch ein Update ersetzen, nicht anzeigen
- Bei jedem Use durch eine Action wird ein **Audit-Eintrag** geschrieben (welches Credential, welche Action, wann)
- Loeschen ist Soft-Delete (archiviert). Endgueltige Loeschung erfolgt durch das Re-Encrypt-Runbook beim naechsten Key-Rotate

## Audit-Log

Im Detail-Tab eines Credentials siehst du, wann es zuletzt verwendet wurde und durch welche Aktion. Praktisch um:

- ungenutzte Credentials zu erkennen und aufzuraeumen
- bei Auffaelligkeiten nachzuvollziehen, welche Rule wann das Credential genutzt hat
- nach einem Token-Leak zu pruefen, ob das alte Credential noch irgendwo aktiv war

## Verwandte Themen

- [Automationen](./automatisierung.md)
- [API: Webhooks und Outbound-Events](../api/webhooks.md)
