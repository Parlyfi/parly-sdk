# Parly SDK

Production SDK for Parly private execution flows.

## What this repo is

This repo contains the public Parly SDK package surface together with the vendored internal helper modules needed to build and validate that package from source.

The primary published developer package is `@parly/sdk`.

## Work from this public repo

```bash
pnpm install
pnpm smoke:standalone
```

## Repository layout

```text
packages/sdk
packages/sdk/src/internal
```

## Release and compatibility

See [COMPATIBILITY.md](./COMPATIBILITY.md) and [versions.json](./versions.json).
