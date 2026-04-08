# Raydo

> Local-first AI workspace for real operations.

[Website](https://raydo.ai) · [GitHub](https://github.com/RaydoAI/Raydo) · [中文说明](./README.zh-CN.md)

![Platform](https://img.shields.io/badge/platform-macOS%20%7C%20Windows%20%7C%20Linux-blue)
![Desktop](https://img.shields.io/badge/desktop-Tauri-orange)
![Frontend](https://img.shields.io/badge/frontend-React%20%2B%20TypeScript-61DAFB)
![Backend](https://img.shields.io/badge/backend-Rust-black)
![Database](https://img.shields.io/badge/database-SQLite-003B57)
![Architecture](https://img.shields.io/badge/architecture-local--first-4f46e5)
![Execution](https://img.shields.io/badge/execution-multi--adapter-0f766e)
![Runtime](https://img.shields.io/badge/runtime-multi--runtime-7c3aed)

Raydo is a local-first AI workspace for teams that need more than a chat surface.

It adds structure around organizations, roles, capabilities, workflows, and execution, while keeping the execution layer flexible enough to work across different adapters and runtimes.

## Why Raydo

AI tools are easy to demo and much harder to operate.

Once work moves beyond a single prompt, teams usually need a more stable layer: who is doing the work, what capabilities are available, how work is routed, where it runs, and how it can be inspected later. Raydo is built for that layer.

## Highlights

### Multi-adapter by design

Raydo is not built around a single model or vendor.

The workspace model stays the same even when the execution layer changes. That matters because product structure should not need to be redesigned every time the underlying adapter changes.

Current direction includes:

- local Codex-style adapters
- local Claude Code-style adapters
- gateway-based execution modes
- room for additional adapters over time

### Multi-runtime, one system

Raydo is designed to run in more than one way without splitting the product into separate tools.

- **Desktop app** for day-to-day use, setup, and operation
- **CLI** for scripting, automation, diagnostics, and operator workflows
- **Manager API / read-only web mode** for inspection, review, and remote acceptance

This makes the same system usable by operators, developers, and delivery teams from different entry points.

### Local-first, delivery-ready

Raydo keeps local execution and control at the center:

- local runtime and local state
- easier auditing and diagnostics
- better fit for restricted environments
- portable packaging and deployment support

That makes it useful both as an internal workspace and as something that can be delivered into real environments.

## Core model

```text
Organization -> Role -> Capability -> Flow -> Execution
```

Raydo treats AI as part of an operating system for work, not as a standalone chat window.

## Current modules

- Dashboard
- Companies
- Templates
- Skills
- Workflows
- Chat
- Channels
- MCP
- Settings

## Use cases

Raydo is a good fit for:

- teams moving from chat-based AI to structured execution
- local-first AI workspaces
- delivery-oriented AI systems
- operator workflows that need desktop, CLI, and remote inspection together
- projects that want adapter flexibility without rebuilding the product around each model

## Stack

- React
- TypeScript
- Tauri
- Rust
- SQLite

The homepage README stays intentionally brief. See the source code and docs for implementation details.

## Quick start

```bash
git clone https://github.com/RaydoAI/Raydo.git
cd Raydo
npm install
npm run tauri:dev
```

## Common commands

```bash
npm run typecheck
npm run test:unit
npm run rust:check
```

CLI:

```bash
cargo run --manifest-path src-tauri/Cargo.toml --bin raydo -- doctor
```

Manager API:

```bash
cargo run --manifest-path src-tauri/Cargo.toml --bin manager_api
```

## Status

Raydo is under active development.

Current priorities:

- a stable workspace model
- a clearer execution path
- a stronger adapter layer
- better consistency across runtimes
- reliable local deployment and delivery

## License

See `LICENSE`.
