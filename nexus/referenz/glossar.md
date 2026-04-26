---
title: Glossar
order: 5
excerpt: Alle wichtigen Begriffe rund um Nexus - von API Key bis window.nx
---

# Glossar

Alphabetische Übersicht aller wichtigen Begriffe, die dir in Nexus begegnen.

**Action** - Ein einzelner Schritt, den eine Automation-Rule oder ein Sequence-Step ausfuehrt, z.B. `ADD_TAG`, `SEND_EMAIL`, `WEBHOOK`, `HTTP_REQUEST`. Insgesamt 23 Actions verfuegbar.

**API Key** - Ein geheimer Schlüssel, mit dem externe Anwendungen auf die Nexus REST API zugreifen können. Wird als `x-api-key` Header gesendet.

**Automation Rule** - Eine Regel im Automations-System, die auf einen einzelnen Trigger reagiert und eine oder mehrere Actions ausfuehrt. Optional mit Conditions (AND/OR) und Variable-Interpolation (`{{userId}}`). Verwaltet unter **Automations > Rules**.

**AVV** - Auftragsverarbeitungsvertrag. Ein nach DSGVO erforderlicher Vertrag zwischen dir (Verantwortlicher) und Nexus (Auftragsverarbeiter) über die Verarbeitung personenbezogener Daten.

**Bounce** - Eine E-Mail, die nicht zugestellt werden konnte. Unterschieden wird zwischen Soft Bounce (temporär, z.B. Postfach voll) und Hard Bounce (dauerhaft, z.B. Adresse existiert nicht).

**Broadcast** - Eine einmalige Newsletter-Nachricht, die an eine bestimmte Empfängergruppe (Segment) gesendet wird.

**Callout** - Ein hervorgehobener Hinweisblock in Nexus-Seiten. Typen: Tipp, Hinweis, Wichtig.

**CNAME** - Ein DNS-Eintrag, der eine Domain auf eine andere weiterleitet. Wird für Custom Domains im Hosting-Bereich benötigt.

**Conversion** - Der Moment, in dem ein Besucher eine gewünschte Aktion ausführt, z.B. einen Kauf abschließt oder sich für den Newsletter anmeldet.

**Credential** - Verschluesselt gespeicherte Zugangsdaten (Bearer-Token, API-Key, Basic-Auth, OAuth2-Client-Secrets, SMTP-Login) fuer die Nutzung in Automations-Actions wie `HTTP_REQUEST` oder `WEBHOOK`. Werte verlassen die API nie im Klartext und werden mit Drei-Schichten-AES-256-GCM-Encryption geschuetzt. Verwaltet unter **Einstellungen > Automations > Credentials**.

**Cookie Consent** - Die Einwilligung des Nutzers zur Verwendung von Cookies. Nexus bietet ein integriertes Cookie-Banner für DSGVO-Konformität.

**CRM** - Customer Relationship Management. In Nexus der Bereich, in dem du Kundendaten, Leads und Kommunikation verwaltest.

**Delivery Action** - Eine produktbezogene automatische Aktion, die im Bereich **Produkt > After-Sales** konfiguriert wird und bei Kauf, Kuendigung oder Erstattung ausgefuehrt wird (z.B. Datei-Download freischalten, Hosting-Instanz provisionieren). Fuer ueber-Produkt-greifende Workflows (CRM, externe Integrationen, mehrstufige Sequenzen) nutze stattdessen das Automations-System unter **Automations**.

**DKIM** - DomainKeys Identified Mail. Ein E-Mail-Authentifizierungsverfahren, das die Echtheit des Absenders bestätigt. Wird über einen DNS-Eintrag konfiguriert.

**DNT** - Do Not Track. Ein Browser-Signal, das Websites auffordert, kein Tracking durchzuführen. Nexus Analytics respektiert dieses Signal.

**DOI** - Double-Opt-In. Ein Verfahren, bei dem Newsletter-Abonnenten ihre Anmeldung per Bestätigungsmail aktiv bestätigen müssen. In Deutschland rechtlich erforderlich.

**DSGVO** - Datenschutz-Grundverordnung. Die europäische Verordnung zum Schutz personenbezogener Daten, die für alle Nexus-Portale gilt.

**Event Occurrence** - Ein einzelner Termin innerhalb einer Event-Serie. Ein wiederkehrendes Event (z.B. wöchentlicher Workshop) hat mehrere Occurrences.

**Fastify** - Das Node.js Web-Framework, auf dem das Nexus-Backend aufgebaut ist. Bekannt für hohe Performance und ein Plugin-basiertes Ökosystem.

**GCLID** - Google Click Identifier. Ein Parameter, der von Google Ads an URLs angehängt wird. Nexus kann diesen Wert im Analytics-Bereich erfassen.

**Handlebars** - Die Template-Engine-Familie, an die sich Nexus anlehnt. In Nexus-Email-Templates kommen einfache Klammern zum Einsatz (`{customer.firstName}`), in Automations-Action-Feldern doppelte Klammern (`{{userId}}`). Siehe [E-Mail Template-Variablen](./email-variablen.md) und [Automationen](../features/automatisierung.md).

**HTML Override** - Die Möglichkeit, einzelne Seiten oder Sektionen im Portal mit eigenem HTML-Code zu überschreiben. Für fortgeschrittene Anpassungen.

**Lead** - Ein potenzieller Kunde, dessen Kontaktdaten im System erfasst sind, der aber noch keinen Kauf getätigt hat.

**Marketplace** - Der Plugin-Marktplatz in Nexus, über den du zusätzliche Funktionen installieren kannst. Enthält offizielle und Community-Plugins.

**MCP** - Model Context Protocol. Eine Schnittstelle, über die KI-Assistenten (z.B. Claude) direkt mit Nexus kommunizieren können.

**Multi-Tenant** - Eine Architektur, bei der eine einzelne Nexus-Installation mehrere unabhängige Portale (Tenants) betreiben kann. Jeder Tenant hat eigene Daten und Konfiguration.

**Next.js** - Das React-Framework, auf dem das Nexus-Frontend (Kundenportal) aufgebaut ist. Bietet Server-Side Rendering und optimierte Performance.

**OG Image** - Open Graph Image. Das Vorschaubild, das beim Teilen einer Seite auf Social Media angezeigt wird. Kann pro Seite und Blogbeitrag konfiguriert werden.

**Plugin** - Eine Erweiterung, die zusätzliche Funktionen zu Nexus hinzufügt. Plugins werden über den Marketplace oder als ZIP-Datei installiert.

**Prisma** - Der Datenbank-ORM, den Nexus intern verwendet. Prisma verwaltet das Datenbankschema und alle Datenbankabfragen.

**Redirect** - Eine Weiterleitung von einer URL auf eine andere. Nützlich für Marketing-Links oder nach einer URL-Änderung.

**REST API** - Die programmatische Schnittstelle von Nexus. Ermöglicht es externen Anwendungen, Daten zu lesen und zu schreiben (Produkte, Bestellungen, Kunden etc.).

**RSS** - Really Simple Syndication. Ein Feed-Format, über das Blog-Beiträge automatisch von Feed-Readern abgerufen werden können.

**Segment** - Eine Teilgruppe deiner Kontakte, gefiltert nach bestimmten Kriterien (z.B. alle Kunden, die Produkt X gekauft haben). Wird für gezielte Newsletter-Kampagnen genutzt.

**Sequence** - Eine mehrstufige Automation aus einem Trigger plus mehreren Schritten mit Wartezeiten dazwischen. Ideal fuer Welcome-Series, Cart-Recovery, Win-Back. Verwaltet unter **Automations > Sequences**. Kontakte werden via Action `ENROLL_IN_SEQUENCE` aus einer Rule hinzugefuegt.

**Slug** - Der URL-freundliche Bezeichner einer Seite, eines Produkts oder Blogbeitrags. Beispiel: `seo-grundlagen` in der URL `/blog/seo-grundlagen`.

**SMTP** - Simple Mail Transfer Protocol. Das Protokoll zum Versenden von E-Mails. Du brauchst einen SMTP-Anbieter (z.B. Mailgun, Brevo), damit Nexus E-Mails verschicken kann.

**SPF** - Sender Policy Framework. Ein DNS-Eintrag, der festlegt, welche Server E-Mails für deine Domain versenden dürfen. Verhindert E-Mail-Spoofing.

**SSL** - Secure Sockets Layer (bzw. TLS). Verschlüsselt die Verbindung zwischen Browser und Server. Nexus-Portale sollten immer über HTTPS (mit SSL) erreichbar sein.

**Stripe** - Der Zahlungsanbieter, den Nexus für Kreditkartenzahlungen, SEPA-Lastschriften und Abonnements nutzt. Stripe wickelt die gesamte Zahlungsabwicklung ab.

**Subscription** - Ein Abonnement, bei dem der Kunde in regelmäßigen Intervallen (monatlich, jährlich etc.) automatisch belastet wird.

**Suppression List** - Eine Liste von E-Mail-Adressen, an die keine E-Mails mehr gesendet werden. Enthält Hard Bounces und manuelle Abmeldungen.

**Template Variable** - Ein Platzhalter in E-Mail Templates, der beim Versand durch einen echten Wert ersetzt wird. In Nexus-Email-Templates: einfache Klammern, z.B. `{customer.firstName}`. In Automation-Actions: doppelte Klammern, z.B. `{{userId}}`.

**Trigger** - Das Ereignis, das eine Automation-Rule oder Sequence startet, z.B. `ORDER_PAID`, `NEW_CONTACT`, `BIRTHDAY`. Insgesamt 30 Trigger verfuegbar, gruppiert nach User-Lifecycle, Order/Payment, Subscriptions, Engagement, CRM, Access und Time.

**Trial Days** - Die Anzahl kostenloser Testtage bei einem Abonnement-Produkt. Während der Trial Phase wird keine Zahlung eingezogen.

**Visual Builder** - Die klickbare Oberflaeche fuer Automation-Rules und Sequences. Trigger, Conditions und Actions per Dropdown waehlen, Variablen per Auto-Complete einfuegen. Synchron mit dem JSON-Editor, der die gleiche Rule als JSON darstellt.

**Webhook** - Eine HTTP-Benachrichtigung, die Nexus oder Stripe an eine URL sendet, wenn ein bestimmtes Ereignis eintritt (z.B. erfolgreiche Zahlung).

**Whitelabel** - Die Möglichkeit, Nexus unter deiner eigenen Marke zu betreiben, ohne dass Nexus als Plattform sichtbar ist. Eigene Domain, eigenes Logo, eigene Farben.

**window.nx** - Das globale JavaScript-Objekt im Kundenportal, über das du per Custom Code auf Nexus-Funktionen zugreifen kannst (z.B. aktuelle Nutzerdaten, Theme-Einstellungen).
