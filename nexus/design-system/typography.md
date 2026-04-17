---
title: Typografie
---

# Typografie

Nexus nutzt die System-Sans-Serif (Shadcn-Standard). Typo-Skala:

## Text-Größen

| Class | Zweck |
|---|---|
| `text-xs` | Labels, Metadaten, Timestamps, List-Rows (Haupttext in dichten Listen) |
| `text-sm` | Body-Text, Button-Inhalt, Banner |
| `text-base` | Default für freie Fließtexte (selten im Admin) |
| `text-lg` | Keine Standard-Nutzung - nur wenn ein Card-Inhalt semantischen Emphasis braucht |
| `text-xl` | Stat-Card-Werte, Card-Titles |
| `text-2xl` | Page-Header (h1) |
| `text-3xl` | Keine Standard-Nutzung - nur für Hero-Sections (Home-Portal), nicht im Admin |

## Font-Weight

| Class | Zweck |
|---|---|
| `font-normal` | Body-Text |
| `font-medium` | Labels, Feld-Namen, Section-Titel |
| `font-bold` | Stat-Card-Werte, Card-Titles |

## Muted vs Primary

- Haupttext: kein extra Color-Class - erbt vom Theme (black/white automatisch).
- Sekundärtext: `text-muted-foreground`.
- Labels in Forms: `<Label>` aus Shadcn.

## Mono-Font

Für Code, IDs, JSON-Snippets, Audit-Log-Diff-Werte:

```tsx
<span className="font-mono text-xs break-all">{id}</span>
```

`break-all` verhindert dass lange IDs das Layout sprengen.

## Truncate

Lange User-Namen, Email-Adressen, Entity-Namen in Listen:

```tsx
<span className="truncate" title={fullValue}>{fullValue}</span>
```

Title-Attribute zeigt den vollen Wert im Tooltip.

## Ueberschriften (H1-H6)

In diesem Admin werden Shadcn `<CardTitle>`, `<CardDescription>` etc. genutzt. Reine HTML-H1/H2-Tags sind selten - bei Bedarf:

```tsx
<h1 className="text-2xl font-bold tracking-tight">Titel</h1>
<p className="text-sm text-muted-foreground">Beschreibung</p>
```

## Don't do

- Keine eigene Font-Family einblenden. Systemfont nutzen oder das explizite Next-Font-Setup aus `app/layout.tsx`.
- Keine `font-thin`, `font-black`. Die Skala ist absichtlich schmal.
- Kein `text-4xl` und grösser in Admin-Seiten.
