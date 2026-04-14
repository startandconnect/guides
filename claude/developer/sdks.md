---
title: SDKs und Agent SDK
order: 2
excerpt: Offizielle Anthropic SDKs und das Agent SDK fuer komplexe Workflows
---

# SDKs und Agent SDK

## Offizielle SDKs

Anthropic pflegt SDKs fuer die gaengigen Sprachen:

- **TypeScript:** `@anthropic-ai/sdk`
- **Python:** `anthropic`
- Weitere: TODO.

TODO: Installation und erstes Beispiel pro Sprache.

## TypeScript Beispiel

```typescript
import Anthropic from "@anthropic-ai/sdk";

const client = new Anthropic();

const response = await client.messages.create({
  model: "claude-sonnet-4-6",
  max_tokens: 1024,
  messages: [{ role: "user", content: "Hallo" }],
});

console.log(response.content);
```

TODO: Beispiele fuer streaming, tool use, structured output.

## Python Beispiel

TODO: Analog fuer Python.

## Agent SDK

Zum Bauen eigener Agents, die Tools aufrufen und mehrstufige Workflows fahren.

TODO: Wann Agent SDK lohnt, Einstiegsbeispiel.

## Wann welches SDK

- **Raw API:** wenn du nur einen einfachen Request machst
- **SDK:** wenn du in TypeScript oder Python bist und mehr als Hello World baust
- **Agent SDK:** wenn du einen echten Agent mit Tools und State baust

TODO: Entscheidungsbaum.

:::tip[Aktuelle Docs]
Die SDKs werden regelmaessig erweitert. Immer die offiziellen Anthropic Docs als primaere Quelle nutzen, nicht alte Tutorials.
:::
