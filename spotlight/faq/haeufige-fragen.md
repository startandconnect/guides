---
title: Haeufige Fragen
order: 1
excerpt: Antworten auf die haeufigsten Fragen zu Spotlight
---

# Häufige Fragen

## Kann ich meinen KI-generierten Code (Claude, ChatGPT, v0) einfach so hosten?

Ja. Kopier das HTML in eine neue Seite, setz den Modus auf `HTML Override > Split`, füg CSS und JS in die passenden Felder. Veröffentlichen — fertig.

## Funktioniert mein React/Vue/Next.js-Projekt?

Spotlight hostet statisches HTML/CSS/JS, keine Server-Side-Rendering-Frameworks. Wenn du dein React-Projekt als statisches Build exportierst (z.B. `npm run build` mit Next.js static export), kannst du die fertigen Files hochladen. Für vollwertige SSR-Apps brauchst du eine andere Hosting-Lösung.

## Kann ich externe APIs aufrufen (OpenAI, Brevo, Airtable)?

Ja — über das [Credential-System](/spotlight/guide/features/credentials). Du legst den API-Key im Admin ab und rufst dann `/api/proxy/<name>/...` aus deinem JavaScript auf. Der Key bleibt serverseitig geheim.

## Kann ich mehrere Domains pro Spotlight-Instanz verbinden?

Aktuell ist eine Hauptdomain pro Instanz vorgesehen. Wenn du mehrere Websites willst, leg dir pro Website eine eigene Spotlight-Instanz an.

## Was ist der Unterschied zu Wix / Squarespace?

Wix und Squarespace sind Website-Builder — du baust deine Seite in deren Editor. Spotlight ist Hosting für Code den du bereits hast. Wenn du einen eigenen HTML/CSS/JS-Stack hast (oder von einer KI generieren lässt), ist Spotlight die passende Lösung. Wenn du per Drag & Drop bauen willst, nimm Wix.

## Was ist der Unterschied zu Netlify / GitHub Pages?

Netlify und GitHub Pages sind für Entwickler — du brauchst Git, Terminal, CI/CD-Verständnis. Spotlight hat ein Admin-Panel: Code reinkopieren, Speichern, live. Außerdem gibt's bei Spotlight fertige Features wie Cookie-Banner, SMTP-Mailversand, Credential-Proxy und Media Library — die musst du bei Netlify alle selbst bauen.

## Wird mein Code bei jeder Änderung deployed?

Nein — sobald du in Spotlight auf **Speichern** klickst, ist die Änderung sofort live. Kein Build-Schritt, kein Warten auf CI/CD.

## Kann ich meine Seite in Git versionieren?

Nicht direkt — Spotlight speichert alles in der Datenbank. Wenn du Git-Versionierung brauchst, kannst du über die API Seiten exportieren und in ein Repo committen. Das ist aber nichts was der Standard-Workflow vorsieht.

## Wo werden meine Daten gespeichert?

Alle Daten liegen auf Servern von **Hetzner in Deutschland** (Nürnberg und Falkenstein). Keine US-Cloud, keine Datentransfers außerhalb der EU, volle DSGVO.

## Wie läuft der Support?

Schreib eine Mail an [support@startandconnect.com](mailto:support@startandconnect.com). Antwort kommt in der Regel innerhalb von 24 Stunden an Werktagen.

## Kann ich mehrere Team-Mitglieder einladen?

Ja — unter **Einstellungen > Team** kannst du weitere Nutzer per E-Mail einladen. Jeder Nutzer bekommt eigene Login-Daten und kann parallel am Content arbeiten.

## Gibt es Backups?

Ja — Spotlight macht täglich automatische Backups deiner Instanz. Im Zweifelsfall können wir dir einen Zustand der letzten 7 Tage wiederherstellen. Schreib uns dafür eine Mail.

## Was passiert wenn ich mein Abo kündige?

Nach Kündigung läuft deine Instanz noch 30 Tage im Grace Period (Instanz offline, Daten bleiben). Danach werden die Daten endgültig gelöscht. Du bekommst vorher noch eine Erinnerung per E-Mail.

## Kann ich von Spotlight später zu Nexus wechseln?

Ja — Nexus bietet alles was Spotlight kann, plus Shop, Newsletter, Events, Affiliate und mehr. Ein Wechsel ist möglich, aber kein Ein-Klick-Import — du müsstest deine Inhalte einmalig migrieren. Die Domain kannst du problemlos mitnehmen.
