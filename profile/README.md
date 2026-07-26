<div align="center">

# lpm

**The package manager for Luau.**

[luaupm.com](https://luaupm.com) · [Browse packages](https://luaupm.com/search) · [Policies](https://luaupm.com/policies)

</div>

---

lpm is a package registry and CLI for the Luau ecosystem. Publish a package
once, install it anywhere Luau runs: Roblox (shared and server), [Lune](https://github.com/lune-org/lune),
[Lute](https://github.com/luau-lang/lute), or plain Luau.

```sh
lpm add alicesaidhi/vide
```

Publishing is just as short. Sign in with GitHub, and your first publish
claims your scope:

```sh
lpm publish
```

## How it works

- **Names are scoped.** Every package is `scope/name`, and a scope belongs to
  the GitHub account that first publishes under it. No name lotteries, no
  squatted global namespace.
- **Versions are immutable.** Once published, a version can never be changed
  or overwritten, only superseded. Your builds stay reproducible.
- **Downloads are free and unlimited.** Package tarballs and the search index
  are served from an edge CDN with no metering, so installing in CI at scale
  costs nothing and needs no token.
- **Everything is open.** The CLI, the registry worker, and the website are
  all in this org, MIT licensed.

## What lives where

| Piece | What it is |
| --- | --- |
| the CLI | Publishes and installs packages, resolves dependencies from `lpm.toml` |
| the registry | Rust worker on Cloudflare that handles publishing, search, and the API |
| the website | [luaupm.com](https://luaupm.com), where you browse packages and read docs |
| the index | Public package metadata and scope ownership, plain files in a repo |

## Status

The registry is young and the ecosystem is small, which is another way of
saying good names are still available. Docs are being written; until they
land, the [website](https://luaupm.com) and the CLI's `--help` are the best
starting points.

Found a bug? Open an issue on the relevant repo. Found a security problem in
a package or in the registry itself? Email
[admin@luaupm.com](mailto:admin@luaupm.com) instead of opening a public
issue. The full rules of the road are at
[luaupm.com/policies](https://luaupm.com/policies).
