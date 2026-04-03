---
title: Kontakte
order: 1
excerpt: Kontaktverwaltung in Nexus
---

# Kontakte

Nexus verfügt über eine integrierte Kontaktverwaltung. Hier kannst du alle deine Kontakte zentral verwalten.

## Kontakte anlegen

Kontakte können auf verschiedene Wege angelegt werden:

1. **Manuell** - Über das Kontakt-Formular im Admin
2. **Import** - CSV-Import für viele Kontakte auf einmal
3. **Automatisch** - Durch Formular-Einsendungen, Newsletter-Anmeldungen oder Bestellungen

## Custom Fields

Du kannst beliebige Custom Fields definieren, um zusätzliche Informationen zu speichern:

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
Custom Fields sind pro Portal individuell konfigurierbar und können jederzeit angepasst werden.
:::

## Listen und Segmente

Organisiere deine Kontakte in Listen:

- **Newsletter** - Alle Newsletter-Abonnenten
- **Kunden** - Kontakte mit mindestens einer Bestellung
- **Leads** - Kontakte die ein Formular ausgefüllt haben

