---
title: Impressum
order: 1
excerpt: Pflichtangaben fuer deine Website einrichten
---

# Impressum

Jede gewerbliche Website in Deutschland braucht ein Impressum (§5 TMG). Spotlight stellt dir eine Vorlage bereit — du musst sie nur befüllen.

## Impressum-Seite anlegen

1. Gehe zu **Seiten > Neue Seite**
2. Titel: `Impressum`
3. Slug: `impressum`
4. Im HTML-Override die untenstehende Vorlage einfügen
5. **Veröffentlichen**

## Vorlage

```html
<h1>Impressum</h1>

<h2>Angaben gemäß § 5 TMG</h2>
<p>
  Max Mustermann<br>
  Musterstraße 1<br>
  12345 Musterstadt
</p>

<h2>Kontakt</h2>
<p>
  Telefon: +49 123 456789<br>
  E-Mail: kontakt@meine-website.de
</p>

<h2>Umsatzsteuer-ID</h2>
<p>
  Umsatzsteuer-Identifikationsnummer gemäß § 27 a Umsatzsteuergesetz:<br>
  DE123456789
</p>

<h2>Redaktionell verantwortlich</h2>
<p>
  Max Mustermann<br>
  (Anschrift wie oben)
</p>
```

## Pflichtangaben-Checkliste

- [x] **Name & Anschrift** — Vollständig, ladungsfähig (keine Postfächer)
- [x] **Kontakt** — E-Mail Pflicht, Telefon empfohlen
- [x] **Vertretungsberechtigte** — Bei GmbH, UG, AG etc.
- [x] **Handelsregister** — Registergericht + Registernummer bei HR-Eintrag
- [x] **USt-IdNr** — Falls vorhanden (nicht jeder hat eine)
- [x] **Aufsichtsbehörde** — Bei bestimmten Berufen (Ärzte, Anwälte, Makler)
- [x] **Berufsbezeichnung & Kammer** — Bei verkammerten Berufen

## Im Footer verlinken

Füge in deinem HTML-Template einen Footer-Link ein:

```html
<footer>
  <a href="/impressum">Impressum</a> ·
  <a href="/datenschutz">Datenschutz</a>
</footer>
```

## Haftungsausschluss

Spotlight stellt nur die Vorlage. Ob dein Impressum rechtssicher ist, kannst nur du (oder dein Anwalt) beurteilen. Bei Unsicherheit empfehlen wir einen Impressumgenerator wie [e-recht24.de](https://www.e-recht24.de/impressum-generator.html) und ggf. eine anwaltliche Prüfung.
