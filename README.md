# limerIQ Releases

Public release distribution for limerIQ:code.

This repository hosts production release assets for limerIQ:code. Source implementation lives in the private `limeriq/limeriq-client` repository.

## Product Overview

limerIQ:code is the governed execution layer for AI-native software delivery.

It turns one-off prompting into reusable workflows that can run in VS Code, in the terminal, or headlessly in CI and automation environments.

Instead of asking one model to do everything in a chat thread, teams define multi-step workflows in YAML that coordinate:

- the latest Claude, Codex, Gemini, and Kimi-Code models
- agentic reasoning plus deterministic execution steps
- code, validation, git, approval, and interactive checkpoints
- cross-repo routing and isolated threads/worktrees
- provider-native permission controls, sandboxing, and execution provenance

The result is a workflow runtime that is reviewable, reproducible, and governable enough to use in real engineering operations.

## Why Teams Use It

- Use the model subscriptions you already have instead of buying a separate orchestration layer
- Turn repeated engineering work into reusable workflows instead of repeating prompts by hand
- Combine AI steps with tests, validation, git operations, approval gates, and trust-chain steps in one runtime
- Keep human oversight where it matters without giving up automation
- Preserve evidence and delivery context instead of losing trust when the chat window closes

## Core Platform Capabilities

- Multi-provider routing across the latest Claude, Codex, Gemini, and Kimi-Code models
- 14 production step types for authoring, including trust-chain steps
- Agent guardrails that can enforce required outputs, expected file actions, retry loops, JSON-schema checks, and code-based compliance checks
- Human-in-the-loop approvals, interactive sessions, and provider-native permission brokering
- Cross-repo orchestration with explicit repo scopes and workflow handoff context
- Threads as the user-facing execution model, backed by isolated git worktrees
- Team workflow repos for canonical, Git-reviewed shared workflows plus local drafts
- Sandboxed execution for worktree-scoped runs using Docker or Apple Container
- Headless and autonomous runner support for CI, queue processing, approval routing, and reporter pipelines
- Execution provenance via evidence bundles, proof-of-execution verification, and attestations
- Marketplace workflow publishing and installation support
- Runtime visualization via subway-map style execution graph

## Current Release Highlights

- Workflows can fail closed when required outputs, files, or compliance checks are missing
- Multi-repo work is explicit and policy-checked instead of improvised
- One thread can own one primary workspace and attach additional repo worktrees over time
- Unattended execution keeps the same guardrails, approval logic, and trust model as interactive execution
- Sandboxed execution can run with staged provider auth instead of ambient host access
- Evidence can be emitted, verified, and bound to run and delivery context

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

## Manual Install From Release Assets

From the latest release: <https://github.com/limeriq/limeriq/releases/latest>

- macOS package: `limeriq-suite-beta.pkg`
- Linux package: `limeriq-suite-beta.deb`
- VS Code extension: `limeriq-*.vsix`

## Source Build / Contribution

Contributors with source access should use `limeriq-client` for build/test/contribution workflows.
