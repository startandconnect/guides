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

TODO: Schritt fuer Schritt, inklusive Homebrew-Alternative.

## Linux

TODO: Schritt fuer Schritt fuer Ubuntu, Debian, Arch.

## Windows (mit WSL)

TODO: WSL aktivieren, Ubuntu installieren, Claude Code im WSL installieren.

## Erster Login

Nach der Installation einmal `claude` starten. Es oeffnet ein Browser-Fenster zum Login.

TODO: Screenshots, was bei Problemen tun.

## Update

Claude Code updated sich nicht automatisch. Alle paar Wochen:

```bash
npm install -g @anthropic-ai/claude-code
```

TODO: Befehl aktuell halten, Release-Notes verlinken.

:::tip[Haeufige Probleme]
Wenn `claude` nicht gefunden wird, ist meist der PATH nicht gesetzt. Siehe Troubleshooting-Abschnitt.
:::
