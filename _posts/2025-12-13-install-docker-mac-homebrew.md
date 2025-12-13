---
layout: post
title: "Installing Docker on Mac with Homebrew: Use --cask"
date: 2025-12-13
category: Tooling
tags: [docker, homebrew, mac, installation]
---

When installing Docker on macOS using Homebrew, the correct command requires the `--cask` flag—nothing else.

## The Right Command

```bash
brew install --cask docker
```

That's it! This installs Docker Desktop for Mac.

## Why --cask?

Docker Desktop is a GUI application, not a command-line formula. Homebrew Cask is designed for managing macOS GUI applications, while regular `brew install` is for command-line tools.

## What Not to Do

Don't try these variations:
- `brew install docker` (installs only CLI tools, not Docker Desktop)
- `brew cask install docker` (outdated syntax, `cask` is now a flag)

## After Installation

Once installed, you can:
1. Launch Docker Desktop from Applications
2. Use `docker` and `docker-compose` commands in your terminal

The `--cask` flag ensures you get the complete Docker Desktop experience with the GUI, Docker Engine, and all the CLI tools.
