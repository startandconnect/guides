---
title: Segment
order: 21
excerpt: Dynamische Kunden-Gruppen fuer Newsletter und Automation
---

# Segment

Dynamische Gruppe von Kunden oder Contacts, definiert durch Filter-Regeln. Im Unterschied zu einer Liste: ein Segment updated sich automatisch. Neue Kunden die die Regeln erfuellen, kommen automatisch rein. Kunden die die Regeln nicht mehr erfuellen, fallen raus.

## Beispiele

- "Kunden aus Deutschland mit aktivem Abo" - Segment-Regeln: country=DE AND subscription.status=active
- "Newsletter-Subscriber ohne Kauf in letzten 90 Tagen" - Segment-Regeln: newsletter.doi=true AND NOT last_purchase_within(90d)
- "Trial-Nutzer, Tag 7-14" - Segment-Regeln: trial.daysActive BETWEEN 7 AND 14

## Wofuer nutzen

- **Newsletter-Versand** an ein Segment statt einer statischen Liste
- **Automations-Filter** - Delivery-Action nur fuer Kunden in Segment
- **Bulk-Aktionen** - "alle im Segment ein Tag geben"
- **Analytics-Split** - Metrics pro Segment separat ansehen

## Nexus-Segment-Editor

Admin unter `/manage/contacts/segments/[id]`. Zeigt:
- Filter-Regeln mit UND/ODER-Toggle
- Live-Preview der aktuell matchenden Kontakte
- Mitglieder-Count in Echtzeit

Regeln auf allen Feldern: Vorname, Email, Tags, Attribute, Subscription-Status, Purchase-History, Engagement, Custom-Fields.

## Segmente vs Listen

- **Segment** - dynamisch, Regel-basiert, Kunden kommen und gehen automatisch
- **Liste** - statisch, du fuegst explizit Kunden hinzu, sie bleiben drin

Fuer "Newsletter-Abonnenten" nimmt man Segment (dynamisch). Fuer "Eingeladene zum Webinar am 15. April" eine Liste (statisch, die Gruppe ist festgelegt).

## SegmentEngine

Technisch: jedes Segment wird durch die SegmentEngine in eine Prisma-Query uebersetzt. Query-Compiler + Preview-Generator im `contacts`-Modul.

Seit v1.3.48 zentral im Core, Newsletter-Plugin nutzt `context.segmentEngine` statt eigener Kopie.

## Preset-Segmente

Vorkonfigurierte Segmente die jede neue Instance automatisch bekommt:
- "Alle Kontakte"
- "Newsletter-Subscriber"
- "Zahlende Kunden"

Seit v1.3.55 editierbar (vorher waren sie gelockt).
