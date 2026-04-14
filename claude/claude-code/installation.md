---
title: Installation
order: 2
excerpt: Claude Code installieren - Mac, Linux, Windows mit WSL
---

# Installation

Claude Code braucht Node.js und ein Terminal. Der Rest ist ein Befehl.

## Voraussetzungen

- Node.js (aktuelle LTS-Version)
- Ein Terminal (Mac: Terminal.app, Linux: bash/zsh, Windows: WSL mit Ubuntu)
- Ein Anthropic Account

TODO: Version-Anforderungen aktualisieren, Links zu Downloads.

## Mac

TODO: Schritt für Schritt, inklusive Homebrew-Alternative.

## Linux

TODO: Schritt für Schritt für Ubuntu, Debian, Arch.

## Windows (mit WSL)

TODO: WSL aktivieren, Ubuntu installieren, Claude Code im WSL installieren.

## Erster Login

Nach der Installation einmal `claude` starten. Es öffnet ein Browser-Fenster zum Login.

TODO: Screenshots, was bei Problemen tun.

## Update

Claude Code updated sich nicht automatisch. Alle paar Wochen:

```bash
npm install -g @anthropic-ai/claude-code
```

TODO: Befehl aktuell halten, Release-Notes verlinken.

:::tip[Häufige Probleme]
Wenn `claude` nicht gefunden wird, ist meist der PATH nicht gesetzt. Siehe Troubleshooting-Abschnitt.
:::
