---
title: Kontakte
order: 1
excerpt: Kontaktverwaltung in Nexus
---

# Kontakte

Nexus verfuegt ueber eine integrierte Kontaktverwaltung. Hier kannst du alle deine Kontakte zentral verwalten.

## Kontakte anlegen

Kontakte koennen auf verschiedene Wege angelegt werden:

1. **Manuell** - Ueber das Kontakt-Formular im Admin
2. **Import** - CSV-Import fuer viele Kontakte auf einmal
3. **Automatisch** - Durch Formular-Einsendungen, Newsletter-Anmeldungen oder Bestellungen

## Custom Fields

Du kannst beliebige Custom Fields definieren, um zusaetzliche Informationen zu speichern:

```json
{
  "fields": [
    { "name": "Firma", "type": "text" },
    { "name": "Branche", "type": "select", "options": ["IT", "Marketing", "Beratung"] },
    { "name": "Umsatz", "type": "number" }
  ]
}
```

:::info
Custom Fields sind pro Portal individuell konfigurierbar und koennen jederzeit angepasst werden.
:::

## Listen und Segmente

Organisiere deine Kontakte in Listen:

- **Newsletter** - Alle Newsletter-Abonnenten
- **Kunden** - Kontakte mit mindestens einer Bestellung
- **Leads** - Kontakte die ein Formular ausgefuellt haben

