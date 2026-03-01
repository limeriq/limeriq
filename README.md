# limerIQ Releases

Public release distribution for limerIQ:code.

This repository hosts production release assets for limerIQ:code. Source implementation lives in the private `limeriq/limeriq-client` repository.

## Product Overview

limerIQ:code turns ad-hoc prompting into repeatable workflow execution.

Instead of asking one model to do everything in a chat thread, teams define multi-step workflows in YAML that combine:

- agentic AI reasoning
- deterministic execution steps (code, validation, git)
- approval and interactive checkpoints
- parallel branches with isolated git worktrees
- provider-native permission controls

The result is a workflow system that is auditable, reproducible, and safer to scale across engineering teams.

## Core Platform Capabilities

- Multi-provider routing across Claude, GPT-5 (Codex transport), and Gemini
- 14 production step types for authoring (task, approval, code, git, validation, interactive, workflow-switch, parallel/integration/consensus/sprint gateways, plus trust-chain steps)
- Persona + prompt-template system for role-specific behavior
- Variable-driven pipelines where outputs flow between steps
- Human-in-the-loop approvals and interactive sessions
- Parallel and multi-repo execution using isolated worktrees
- Marketplace workflow publishing and installation support
- Runtime visualization via subway-map style execution graph

## Architecture At A Glance

limerIQ:code uses a strict three-layer architecture:

1. UI surfaces: VS Code extension + webviews
2. CLI orchestration layer: lifecycle, permissions, routing, marketplace
3. Execution engine: step handlers, context, variable resolution, workflow runtime

Design rules:

- CLI owns business logic
- UI remains a thin presentation/control layer
- Prompt behavior is template-driven (no hardcoded prompt logic)
- Step handlers define capability boundaries

## Release Channels

- GitHub releases: <https://github.com/limeriq/limeriq/releases>
- Homebrew tap: <https://github.com/limeriq/homebrew-tap>

## Install and Update

### macOS

Install via Homebrew:

```bash
brew tap limeriq/homebrew-tap
brew install --cask limeriq
```

To update:

```bash
brew update
brew upgrade --cask limeriq
```

### Linux / WSL2

Install with a single command:

```bash
curl -fsSL https://limeriq.ai/install.sh | bash
```

To update, run the same command again:

```bash
curl -fsSL https://limeriq.ai/install.sh | bash
```

Note: as of March 1, 2026, unauthenticated requests to `https://limeriq.ai/install.sh` are redirecting to a sign-in HTML page rather than a shell script. If that remains true in your environment, install from GitHub release assets (`.deb` on Linux/WSL2).

## Manual Install From Release Assets

From the latest release: <https://github.com/limeriq/limeriq/releases/latest>

- macOS package: `limeriq-suite-beta.pkg`
- Linux package: `limeriq-suite-beta.deb`
- VS Code extension: `limeriq-*.vsix`

## Source Build / Contribution

Contributors with source access should use `limeriq-client` for build/test/contribution workflows.
