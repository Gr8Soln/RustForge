# RustForge

A progressive, project-based Rust engineering workshop — 50+ projects taking me from Rust fundamentals to production-grade systems engineering, plus the reusable libraries, CLI tools, and services that come out of it.

[![CI](https://github.com/Gr8Soln/RustForge/actions/workflows/ci.yml/badge.svg)](https://github.com/Gr8Soln/RustForge/actions/workflows/ci.yml)
[![License: MIT OR Apache-2.0](https://img.shields.io/badge/license-MIT%20OR%20Apache--2.0-blue.svg)](#license)

## Quickstart

```bash
git clone https://github.com/Gr8Soln/RustForge.git
cd RustForge
cargo build --workspace
cargo test --workspace
```

Run a specific project or app:

```bash
cargo run -p <project-or-crate-name>
```

Browse the full roadmap, phase-by-phase project list, and repository architecture rationale in [`docs/roadmap.md`](docs/roadmap.md).

## What this is — and isn't

This repo is a learning workshop, not a single product. It contains:

- **`projects/`** — standalone, independently-readable implementations from the learning roadmap (Phases 1–2 mostly live here).
- **`crates/`** — reusable libraries (`rf-*`) with documented public APIs, meant to be depended on by other code in this repo and, where noted, published to crates.io.
- **`apps/`** — CLI tools and services meant to be run, not just read (e.g. `taskline`, `portscan-rs`).
- **`experiments/`** — explicitly throwaway work: unsafe spikes, performance experiments, API sketches that didn't make the cut.
- **`docs/`** — architecture notes (one short ADR per project with a real design decision) and a running learning log.

It is **not** a single cohesive application — different directories are at very different levels of polish depending on which phase of the roadmap they belong to. Phase 1–2 projects are learning exercises; projects flagged in the roadmap as independent-repo candidates will eventually move out of this workspace entirely.

## Repository structure

```
RustForge/
├── Cargo.toml              # workspace root, shared [workspace.dependencies]
├── rust-toolchain.toml     # pinned toolchain
├── .github/workflows/      # ci.yml, audit.yml, release.yml
├── projects/                # standalone learning projects
├── crates/                  # reusable libraries (rf-*)
├── apps/                    # CLI tools and services
├── experiments/             # throwaway / exploratory work
├── docs/
│   ├── architecture/        # one ADR per project with a real design decision
│   ├── roadmap.md           # the full 56-project roadmap
│   └── learning-log.md      # concept → project → what clicked
└── scripts/                  # repo automation
```

Workspace and naming conventions, testing/benchmarking conventions, and the full rationale behind this layout are documented in [`docs/roadmap.md`](docs/roadmap.md#2-repository-architecture).

## Testing

```bash
cargo test --workspace          # unit + integration tests
cargo clippy --workspace -- -D warnings
cargo fmt --all -- --check
cargo bench -p <crate-name>     # where benchmarks exist (criterion)
```

CI runs the same checks on every PR, plus `cargo-deny` for license/advisory auditing once a crate has external dependencies.

## Status

Actively in progress, moving through the roadmap phase by phase. See [`docs/roadmap.md`](docs/roadmap.md) for current progress and what's next.

## License

Dual-licensed under [MIT](LICENSE-MIT) or [Apache-2.0](LICENSE-APACHE), at your option.