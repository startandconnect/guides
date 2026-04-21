---
title: KI und LLM
order: 2
excerpt: Was hinter ChatGPT, Claude und Co. steckt
---

# KI und LLM

## KI (Kuenstliche Intelligenz)

Sammelbegriff fuer Software die Dinge tut, die man frueher nur Menschen zugetraut hat: Text verstehen, Bilder erkennen, Muster finden, Entscheidungen treffen. Umfasst ganz unterschiedliche Techniken - Regel-Systeme, maschinelles Lernen, neuronale Netze.

## LLM (Large Language Model)

Eine bestimmte Art von KI: Sprachmodelle, trainiert auf riesigen Textmengen, die daraufhin menschenaehnlich schreiben, fragen beantworten, Code schreiben. Claude ist ein LLM. GPT ist ein LLM. Gemini ist ein LLM.

## Generative KI

KI die neue Inhalte erzeugt: Texte, Bilder, Musik, Code. Im Unterschied zu "klassischer" KI die nur klassifiziert (Spam oder kein Spam) oder vorhersagt (Kunde wird kuendigen).

## Prompt

Die Eingabe, die du einem LLM gibst. Gute Prompts sind praezise, liefern Kontext, zeigen Beispiele. Schlechte Prompts sind vage oder zu kurz. "Schreib mir einen Newsletter" vs "Schreib mir einen Newsletter fuer Bestandskunden meines Online-Kurses zum Thema Gewohnheiten, Tonalitaet locker aber kompetent, 400 Wörter, mit 3 konkreten Tipps."

## Context Window

Wie viel Text das LLM in einem Schritt lesen kann. Claude hat aktuell 200k Tokens (etwa 150k Wörter oder 500 Seiten). Alles was darueber hinaus geht: muss weg oder zusammengefasst werden.

## Agent

Ein LLM das nicht nur antwortet sondern Tools benutzt: Web durchsucht, Code ausfuehrt, APIs aufruft, Daten liest. Claude Code ist ein Agent. ChatGPT mit Tools ist ein Agent.

## MCP (Model Context Protocol)

Offener Standard wie Agents mit externen Tools reden. Nexus ist MCP-ready - Claude kann direkt Nexus-API-Calls ausfuehren. Siehe [MCP](/glossar/technik-und-api/mcp).
