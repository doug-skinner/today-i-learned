---
layout: post
title: "Biome: One Tool to Replace ESLint and Prettier"
date: 2025-12-10
category: Tooling
tags: [biome, linting, formatting, javascript]
---

I recently discovered [Biome](https://biomejs.dev/), a fast toolchain that combines linting and formatting in a single tool—replacing both ESLint and Prettier.

## Why It's Great

- **Fast**: Written in Rust, it's significantly faster than ESLint + Prettier
- **All-in-one**: No more juggling two separate configs and running two commands
- **Drop-in replacement**: Compatible with most ESLint and Prettier rules
- **Zero config**: Works out of the box with sensible defaults

## Quick Start

```bash
npm install --save-dev --save-exact @biomejs/biome
npx @biomejs/biome init
```

Then run:

```bash
npx @biomejs/biome check --write ./src
```

That's it! One command to lint and format your code.
