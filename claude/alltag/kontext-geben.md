---
title: Kontext geben - das Kernprinzip
order: 3
excerpt: Warum guter Kontext mehr bringt als guter Prompt
---

# Kontext geben - das Kernprinzip

Wenn du nur eine Sache aus diesem Guide mitnimmst, dann das: **Kontext schlägt Kunst.** Ein mittelmäßiger Prompt mit viel Information ist besser als ein eleganter ohne.

## Was ist Kontext

Kontext ist alles, was Claude über deine Situation weiß:

- Wer du bist (Rolle, Erfahrungslevel)
- Was du vorhast (Ziel, nicht nur die nächste Aufgabe)
- Was du schon probiert hast
- Welche Beschränkungen gelten (Zeit, Budget, Format)
- Beispiele für gewünschtes Ergebnis

## Minimal-Beispiel vs Kontext-Beispiel

Gleiche Aufgabe, völlig unterschiedliche Ergebnisse.

### Ohne Kontext

> Schreib mir eine Stellenanzeige für einen Designer.

Was du bekommst: generische Stellenanzeige. "Wir sind ein dynamisches Team das Innovationen vorantreibt", die üblichen Phrasen, vermutlich englisch durchsetzt, nichts was deine Firma von der nächsten unterscheidet.

### Mit Kontext

> Schreib mir eine Stellenanzeige für eine Designer-Stelle.
>
> Firma: kleine SaaS-Agentur in Kiel, 4 Personen, wir bauen eigene Produkte und betreuen einige Kunden.
>
> Wir suchen: Senior-Designer:in (3+ Jahre) für Mix aus UX/UI für SaaS-Apps und Marketing-Material. Remote möglich, Office in Kiel verfügbar.
>
> Was uns wichtig ist: Direkter Kommunikation, kein Bullshit-Bingo, Eigeninitiative. Wir bezahlen marktüblich (wir sind keine Konzern).
>
> Stil der Anzeige: ehrlich, konkret, kurz. Nicht "wir sind dynamisch und passioniert". Lieber Details über die Arbeit als Floskeln.
>
> Beispiele für unseren Tonfall: schau auf startandconnect.com/karriere wenn was da ist.

Was du bekommst: eine Anzeige die nach deiner Firma klingt, konkrete Aufgaben benennt, ehrlich ist. Vielleicht 80 Prozent fertig.

## Woher kommt der Kontext

### Du schreibst ihn

Im Prompt, als erstes. Wer du bist, was du willst, was wichtig ist. Funktioniert immer, kostet aber jedes Mal Tipparbeit.

**Beispiel:** Du startest jeden zweiten Chat mit einer Standard-Einleitung "Ich bin Freelance-Designerin, arbeite primär mit Startups, mein Stil ist X." Das ist ineffizient.

### Du hängst ihn an

Dateien, Bilder, Screenshots. Im Web-Chat per Drag-and-Drop, in der Claude App durch den verbundenen Workspace.

**Beispiel:** Du lädst eine PDF mit Style-Guide hoch. Claude liest die ganze PDF und nutzt sie als Referenz für die Antwort. Du musst nicht den Stil im Prompt beschreiben.

### Du machst ihn permanent

In der Web-Variante: Projects mit dauerhaft hinterlegten Anweisungen.
In der Claude App: CLAUDE.md im Workspace + globale Anweisungen in den App-Einstellungen.

**Beispiel:** Du hinterlegst einmalig "Ich bin Freelance-Designerin, mein Stil ist X" in den globalen Anweisungen. Ab jetzt weiß Claude das in jedem Chat. Sparst dir das Wiederholen.

Der dritte Weg ist am wertvollsten - permanenter Kontext ist der größte einzelne Hebel den Claude bietet.

## Anti-Muster

### Einzeilige Prompts ohne Hintergrund

**Schlecht:** "Schreib mir eine Mail."
**Besser:** "Schreib mir eine Mail an Max (Kunde, hat Angebot abgelehnt) mit Tonfall freundlich-professionell, kurz halten, Tür offen lassen für später."

### Zu höflich

**Schlecht:** "Könntest du vielleicht, wenn es nicht zu viel Mühe macht, eventuell überlegen ob du mir bei einer kleinen Sache helfen könntest?"
**Besser:** "Hilf mir bei X."

Höflichkeit gegenüber KI bringt nichts und kostet Tokens. Sei direkt, das ist effizient und Claude reagiert nicht beleidigt.

### Über-spezifische Beispiele

Wenn du zu stark ein konkretes Beispiel vorgibst, kopiert Claude es statt zu verstehen.

**Schlecht:** "Schreib mir 10 Newsletter-Titel. Hier ist ein Beispiel: 'So sparst du 80 Prozent Zeit mit Tool X'." Du bekommst 10 Variationen davon, alle mit Prozent-Zahl.

**Besser:** "Schreib mir 10 Newsletter-Titel zum Thema Y. Hier sind drei Beispiele für meinen Stil: ... Jeder Titel sollte konkret und neugierig machen, kein Marketing-Sprech."

Mehrere Beispiele zeigen ein Muster, ein einzelnes wird kopiert.

### Zu vage Anweisungen

**Schlecht:** "Mach es kreativ."
**Besser:** "Mach es überraschender. Bring eine ungewöhnliche Perspektive rein, z.B. wie XYZ das Thema sieht."

"Kreativ" ist nicht messbar. "Überraschend" ist eine Richtung, "Perspektive XYZ" ist konkret.

### Mehrere Themen in einem Prompt

**Schlecht:** "Schreib mir eine Mail an Max, dann eine Stellenanzeige für einen Designer und überleg auch noch ob ich diese Idee verfolgen soll."

Drei Aufgaben, drei mittelmäßige Antworten. Lieber: drei Chats für drei Aufgaben.

## Praktischer Test

Bevor du einen Prompt absendest: lies ihn einmal durch und frag dich:

- Könnte jemand ohne meinen Kontext das beantworten?
- Wenn ja: Claude wird auch raten. Ergänze Kontext.
- Wenn nein: gut, der Prompt steht.

:::tip[Praxis]
Permanenter Kontext (CLAUDE.md, Projects, App-Einstellungen) ist der wichtigste Hebel. Wer hier 30 Minuten investiert, spart Wochen kumulativer Tipparbeit.
:::
