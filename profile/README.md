<div align="center">

<a href="https://luaupm.com">
  <img src="https://luaupm.com/lpm-logo.png" alt="lpm logo" width="110" />
</a>

# lpm

**The package manager for Luau.**

<a href="https://luaupm.com"><img src="https://img.shields.io/badge/luaupm.com-e61048?style=flat-square&logoColor=white" alt="Website" /></a>
<a href="https://luaupm.com/search"><img src="https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fcdn.luaupm.com%2Fstats.json&query=%24.packages&label=packages&color=e61048&style=flat-square" alt="Packages" /></a>
<a href="https://luaupm.com"><img src="https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fcdn.luaupm.com%2Fstats.json&query=%24.downloads_total&label=downloads&color=e61048&style=flat-square" alt="Downloads" /></a>
<a href="https://discord.gg/NYfNd7yq5n"><img src="https://img.shields.io/badge/discord-5865F2?style=flat-square&logoColor=white" alt="Discord" /></a>
<img src="https://img.shields.io/badge/license-MIT-2ea44f?style=flat-square" alt="MIT license" />

[Browse packages](https://luaupm.com/search) · [Docs](https://luaupm.com/docs) · [Policies](https://luaupm.com/policies) · [Discord](https://discord.gg/NYfNd7yq5n)

</div>

---

lpm is a package registry and CLI for the Luau ecosystem. Publish a package
once, install it anywhere Luau runs: Roblox (shared and server), [Lune](https://github.com/lune-org/lune),
[Lute](https://github.com/luau-lang/lute), or plain Luau.

```sh
cargo install luaupm   # crate is luaupm, binary is lpm
lpm self install       # puts lpm and lpx on PATH
```

Prebuilt binaries are on the [latest release](https://github.com/luaupm/cli/releases/latest);
run `lpm self install` on those too. Full instructions: [Installing LPM](https://luaupm.com/docs/installation).

Adding a dependency is one command:

```sh
lpm add chief/core
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
- **Wally and pesde packages work too.** lpm resolves and installs from both
  existing registries, so you don't need the ecosystem to move before you do.

## More than dependencies

The CLI covers the rest of a Luau project too:

- `lpm tool` pins GitHub-released binaries like Rojo and darklua per project
  or globally, and `lpx` runs one without installing it.
- `lpm run` runs your project scripts with those pinned tools on PATH.
- `lpm studio` opens what the project edits in Roblox Studio.
- Workspaces keep a monorepo of packages in one manifest tree.
- `lpm self` also wires up manifest IntelliSense in your editor.

## What lives where

| Repo | What it is |
| --- | --- |
| [cli](https://github.com/luaupm/cli) | The lpm binary. Installs, publishes, resolves `lpm.toml`, pins tools, runs scripts |
| [index](https://github.com/luaupm/index) | Public package metadata and scope ownership, plain files in a repo |

The registry worker behind publishing, search, and the API, along with
[luaupm.com](https://luaupm.com) itself, aren't publicly available. The CLI and
the index are MIT licensed.

## Status

The registry is young and the ecosystem is small, which is another way of
saying good names are still available. The [docs](https://luaupm.com/docs)
cover every command, the manifest, and the registry internals; [sharp
edges](https://luaupm.com/docs/sharp-edges) collects the behavior that
surprises people.

Found a bug? Open an issue on the relevant repo, or ask in
[Discord](https://discord.gg/NYfNd7yq5n). Found a security problem in a
package or in the registry itself? Email
[admin@luaupm.com](mailto:admin@luaupm.com) instead of opening a public
issue. The full rules of the road are at
[luaupm.com/policies](https://luaupm.com/policies).
