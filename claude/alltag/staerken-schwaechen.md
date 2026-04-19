---
title: Stärken und Schwächen
order: 2
excerpt: Wofür Claude richtig gut ist - und wofür nicht
---

# Stärken und Schwächen

Wer Claude realistisch einschätzt, bekommt bessere Ergebnisse. Hype und Panik helfen beide nicht.

## Wo Claude stark ist

**Strukturieren von Gedanken**

Du hast einen Haufen roher Notizen, eine wirre Idee, ein Argument das du nicht greifen kannst.

**Beispiel:** "Ich überlege ob ich mich selbstständig machen soll. Hier sind 50 Gedanken die ich dazu hatte. Strukturier sie nach Themen, finde die zentralen Spannungsfelder, frag mich zurück wo es widersprüchlich ist."

Claude erstellt Cluster, identifiziert die Kernfragen, gibt dir was zum Weiterdenken.

**Programmieren**

Boilerplate, Refactoring, Bugs erklären, Tests schreiben.

**Beispiel:** "Hier ist eine Funktion in Python die manchmal abstürzt. Hier ist die Fehlermeldung. Was übersehe ich?" Claude erklärt das Problem in einfachen Worten und schlägt einen Fix vor.

**Übersetzen und Umformulieren**

Zwischen Sprachen, zwischen Formalitätsstufen, zwischen Zielgruppen.

**Beispiel:** "Übersetze diese Mail ins Englische, behalte den freundlich-direkten Ton." Oder: "Schreib diesen formellen Text als WhatsApp-Nachricht für einen guten Freund um."

**Dokumente verstehen**

Lange PDFs zusammenfassen, Unterschiede zwischen Versionen, wichtige Stellen finden.

**Beispiel:** Ein 80-seitiger Vertrag. "Was sind die Risiken für mich als Auftragnehmer? Welche Klauseln sollte ich verhandeln?" Claude liest, analysiert, antwortet konkret.

**Brainstormen**

20 Ideen in einer Minute, danach filtern.

**Beispiel:** "Ich brauche zehn alternative Titel für diesen Blogartikel. Mix aus sachlich und provokant. Hier ist der Artikel..."

## Wo Claude schwach ist

**Exakte Zahlen**

Rechnet, aber nicht immer richtig. Auch bei einfachen Aufgaben.

**Beispiel:** "Was ist 17 Prozent von 4287?" - Claude antwortet vermutlich richtig, aber nicht garantiert. Wenn die Antwort wichtig ist: Taschenrechner oder Claude bitten ein Script zu schreiben statt selbst zu rechnen.

**Gegenmaßnahme:** für kritische Berechnungen "Schreib mir ein Python-Snippet das das ausrechnet" - Code rechnet immer richtig.

**Aktuelle Ereignisse**

Wissensstand ist meist Monate alt. Was letzte Woche passiert ist, weiß Claude oft nicht.

**Beispiel:** "Was waren die wichtigsten Tech-News diese Woche?" - Claude wird raten oder ehrlich sagen "nicht aktuell".

**Gegenmaßnahme:** Connectors zu Web-Suche oder spezifischen Quellen aktivieren, dann kann Claude live recherchieren.

**Persönliche Daten über Personen**

Vermischt Quellen, erfindet Details. Bei prominenten Personen relativ sicher, bei weniger bekannten oft Halluzinationen.

**Beispiel:** "Wer ist [Name einer halb-bekannten Person]?" - Claude rät, vermischt mit ähnlichen Namen, erfindet Details. Niemals als Quelle für Personen-Recherche nutzen.

**Gegenmaßnahme:** echte Quellen (LinkedIn, persönliche Website) nutzen.

**"Nein" sagen bei schlechten Ideen**

Ist oft zu höflich. Wenn du eine schlechte Idee hast und Claude um Feedback bittest, kommt eher Beschönigung als ehrliche Kritik.

**Beispiel:** "Ich will eine App bauen die WhatsApp ersetzt." - Claude wird Vorteile finden statt klar zu sagen "der Markt ist gesättigt, Differenzierung extrem schwer".

**Gegenmaßnahme:** explizit fragen: "Spiel Devil's Advocate. Was sind die drei stärksten Argumente gegen meine Idee?"

**Konsistenz über lange Chats**

Vergisst frühe Details, widerspricht sich. Bei sehr langen Chats kommt es vor dass Claude sich an Definitionen vom Anfang nicht mehr erinnert.

**Beispiel:** Du definierst zu Beginn "Kunde A" als XY, nach 50 Nachrichten ist diese Definition vergessen oder verdreht.

**Gegenmaßnahme:** wichtige Definitionen in Dateien schreiben (CLAUDE.md, context.md), nicht nur im Chat. Bei langen Themen neuen Chat öffnen mit klarem Briefing.

## Die Metaregel

Claude ist kein Orakel, sondern ein sehr schneller, sehr belesener Praktikant. Behandle die Antworten so.

**Was diese Metapher konkret heißt**

| Praktikant | Claude |
|---|---|
| Hat viel gelesen, weiß viel | wie ein Praktikant |
| Macht Anfängerfehler bei Detail | wie ein Praktikant |
| Weiß nicht was wichtig ist und was nicht (ohne Briefing) | wie ein Praktikant |
| Sagt selten "nein, das ist Quatsch" | wie ein Praktikant |
| Du musst Ergebnisse prüfen | wie ein Praktikant |
| Ist manchmal genial | wie ein Praktikant |
| Wird besser je klarer dein Briefing | wie ein Praktikant |

**Vergleich mit anderen Rollen**

Claude ist NICHT:

- **Ein Senior Consultant:** der würde dir bei wichtigen Entscheidungen widersprechen, Claude eher nicht
- **Ein Lehrer:** der würde dich auf Lücken hinweisen, Claude antwortet meist auf das was du fragst
- **Ein Kollege auf Augenhöhe:** der hat Skin in the Game, Claude nicht
- **Eine Suchmaschine:** die zeigt dir Quellen, Claude generiert Antworten

Wer Claude wie einen Senior behandelt, wird enttäuscht. Wer Claude wie einen schnellen, hilfsbereiten Praktikanten behandelt, ist produktiv.

:::tip[Wichtig]
Bei jeder wichtigen Antwort: kurz fragen "Würde ich das einem Praktikanten ungeprüft glauben?" Wenn nein: prüfen, querchecken, eigenes Urteil dazugeben.
:::
