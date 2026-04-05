---
title: Navigation & Footer
order: 2
excerpt: Header, Footer und Menüs für verschiedene Benutzergruppen konfigurieren
---

# Navigation & Footer

Nexus bietet drei getrennte Navigationen für verschiedene Benutzergruppen. Jede Gruppe sieht nur die für sie relevanten Menüpunkte.

## Drei Navigationen

Unter **Einstellungen > Navigation** konfigurierst du separate Menüs:

- **Besucher** - Nicht eingeloggte Nutzer sehen z.B. "Produkte", "Über uns", "Login"
- **Team** - Eingeloggte Team-Mitglieder sehen z.B. "Dashboard", "Kunden", "Produkte"
- **Kunden** - Eingeloggte Kunden sehen z.B. "Mein Bereich", "Bestellungen", "Support"

## Menüpunkte verwalten

Für jede Navigation kannst du:

- **Menüpunkte hinzufügen** - Titel und URL angeben
- **Sortierung ändern** - Per Drag & Drop die Reihenfolge anpassen
- **Untermenüs erstellen** - Punkte verschachteln für Dropdown-Menüs
- **Sichtbarkeit steuern** - Einzelne Punkte aktivieren/deaktivieren

## CTA Button

Jede Navigation hat einen optionalen Call-to-Action Button im Header:

- **Text** - z.B. "Jetzt starten" oder "Login"
- **URL** - Ziel-Link
- **Stil** - Wird als hervorgehobener Button dargestellt

:::tip[Tipp]
Zeige Besuchern einen "Registrieren" CTA und Kunden einen "Mein Bereich" CTA - so ist die Navigation immer kontextgerecht.
:::

## Footer konfigurieren

Unter **Einstellungen > Navigation > Footer**:

- **Spalten** - Mehrere Spalten mit Überschrift und Links
- **Copyright** - Text in der Fußzeile
- **Social Links** - Links zu Social-Media-Profilen

## Legal Links

Legal Links werden automatisch im Footer angezeigt:

- **Impressum** - Pflicht in DACH
- **Datenschutzerklärung** - Pflicht bei Datenverarbeitung
- **AGB** - Bei Verkauf empfohlen

Die Inhalte dieser Seiten konfigurierst du unter **Einstellungen > Inhalte > Legal**.

## HTML Override

Für volle Kontrolle über Header und Footer:

1. Aktiviere den **HTML Override** in den Navigations-Einstellungen
2. Schreibe eigenes HTML mit eingebettetem CSS und JavaScript
3. Dein Code ersetzt den Standard-Header bzw. Footer komplett

Du kannst separate Overrides pro Benutzergruppe (Besucher, Team, Kunden) konfigurieren.

```html
<!-- Beispiel: Einfacher Custom Header -->
<header style="display:flex; justify-content:space-between; padding:1rem;">
  <a href="/">Mein Portal</a>
  <nav>
    <a href="/produkte">Produkte</a>
    <a href="/kontakt">Kontakt</a>
  </nav>
</header>
```

:::warning[Wichtig]
Bei aktivem HTML Override bist du selbst für Responsive Design und Barrierefreiheit verantwortlich. Der Standard-Header passt sich automatisch an.
:::
