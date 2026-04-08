# Raydo

> 本地优先的 AI 工作台，用来承接真实业务执行。

[官网](https://raydo.ai) · [GitHub](https://github.com/RaydoAI/Raydo) · [English](./README.md)

![Platform](https://img.shields.io/badge/platform-macOS%20%7C%20Windows%20%7C%20Linux-blue)
![Desktop](https://img.shields.io/badge/desktop-Tauri-orange)
![Frontend](https://img.shields.io/badge/frontend-React%20%2B%20TypeScript-61DAFB)
![Backend](https://img.shields.io/badge/backend-Rust-black)
![Database](https://img.shields.io/badge/database-SQLite-003B57)
![Architecture](https://img.shields.io/badge/architecture-local--first-4f46e5)
![Execution](https://img.shields.io/badge/execution-multi--adapter-0f766e)
![Runtime](https://img.shields.io/badge/runtime-multi--runtime-7c3aed)

Raydo 是一套本地优先的 AI 工作台，面向那些不满足于“只是聊天”的团队。

它试图把组织、角色、能力、流程和执行放进同一个系统里，同时让底层执行层保持足够灵活，能够承接不同 adapter 和不同 runtime。

## 为什么是 Raydo

AI 产品做演示并不难，难的是进入真实工作。

一旦事情不再是一次性 prompt，团队通常就需要更稳定的一层：谁在执行、能调用什么能力、任务如何流转、运行在哪里、后续如何检查。Raydo 关注的就是这一层。

## 产品特点

### 从一开始就考虑多 Adapter

Raydo 不围绕单一模型或单一厂商来设计。

即使底层执行层发生变化，工作台结构、角色模型和流程模型也尽量保持稳定。这样做的意义很直接：底层变了，产品层不需要跟着反复重做。

当前方向包括：

- 本地 Codex 类 adapter
- 本地 Claude Code 类 adapter
- 网关式执行模式
- 后续更多 adapter 的扩展空间

### 多 Runtime，而不是单入口工具

Raydo 不是一个只能从单一入口使用的工具，而是一套可以在不同 runtime 下工作的系统。

- **桌面应用**：用于日常使用、配置和操作
- **CLI**：用于脚本化、自动化、诊断和运维场景
- **Manager API / 只读 Web 模式**：用于巡检、查看、验收和远程只读访问

这样同一套系统就可以同时服务操作人员、开发人员和交付团队，而不需要拆成几套割裂的工具。

### 本地优先，但也适合交付

Raydo 把本地运行和可控性放在核心位置：

- 本地运行时和本地状态
- 更容易审计和诊断
- 更适合受限网络环境
- 支持便携化打包和部署

所以它不只适合自己使用，也适合真正落到客户环境或团队环境中。

## 核心结构

```text
Organization -> Role -> Capability -> Flow -> Execution
```

也就是：

```text
组织 -> 角色 -> 能力 -> 流程 -> 执行
```

在 Raydo 里，AI 不是一个独立聊天框，而是工作系统里的执行单元。

## 当前模块

- Dashboard
- Companies
- Templates
- Skills
- Workflows
- Chat
- Channels
- MCP
- Settings

## 适合的场景

Raydo 当前更适合这些场景：

- 想把 AI 从对话工具升级成执行系统的团队
- 需要本地优先 AI 工作台的项目
- 面向交付的 AI 系统
- 同时需要桌面、CLI 和远程巡检入口的工作环境
- 希望支持多 adapter，但又不想围绕每个模型重做产品结构的项目

## 技术栈

- React
- TypeScript
- Tauri
- Rust
- SQLite

首页 README 保持简洁，具体实现细节建议直接看代码和 docs。

## 快速开始

```bash
git clone https://github.com/RaydoAI/Raydo.git
cd Raydo
npm install
npm run tauri:dev
```

## 常用命令

```bash
npm run typecheck
npm run test:unit
npm run rust:check
```

CLI：

```bash
cargo run --manifest-path src-tauri/Cargo.toml --bin raydo -- doctor
```

Manager API：

```bash
cargo run --manifest-path src-tauri/Cargo.toml --bin manager_api
```

## 项目状态

Raydo 正在持续迭代中。

当前阶段重点：

- 更稳定的工作台结构
- 更清晰的执行链路
- 更完整的 adapter 层
- 更一致的多 runtime 体验
- 更可靠的本地部署与交付能力

## License

See `LICENSE`.
