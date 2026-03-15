# Semantic Voxel Protocol
<div align="center">
  <img src="../logo/logo.png" alt="SVP Logo" />
  <p><strong>Cognitive Infrastructure for AI-Human Collaborative Programming</strong></p>
</div>

---

<div align="center">

**English | [日本語](./README_JP.md) | [中文](./README_ZH.md)**

</div>

---
## What is SVP?
SVP (Semantic Voxel Protocol) is an intent‑driven software compilation paradigm designed for the AI era—a design philosophy that reshapes the boundary of human–machine collaboration. SVP transforms discrete software designs into machine‑readable intermediate representations (IR) and establishes a rigorous five‑layer architecture (L5 Intent Layer → L4 Architecture Layer → L3 Logic Layer → L2 Skeleton Layer → L1 Implementation Layer) to ensure that developers’ intentions are faithfully executed.

It emulates classical compiler principles, allowing only top‑down, unidirectional compilation and strictly prohibiting any bottom‑up modifications to synchronize higher layers. SVP is a foundational methodology for resisting systemic entropy.

## Why SVP?

Current AI coding tools (Cursor, Claude Code, GitHub Copilot) operate at the **text/code level**, leading to:

- **Context overflow**: AI chokes on large codebases, unable to maintain coherent understanding across thousands of files
- **Destructive edits**: AI "fixes" often break carefully crafted human logic, introducing subtle bugs
- **Architecture drift**: No semantic guardrails—system structure gradually erodes into spaghetti code
- **Review nightmare**: Humans must audit thousands of lines of generated code, defeating the purpose of AI assistance

**The root cause**: AI is working at the wrong abstraction layer. It's like trying to understand a novel by analyzing individual ink molecules.

> Just as humans don't write machine code, AI shouldn't directly manipulate source code.

SVP introduces **Layered Compilation**—a classic software engineering approach adapted for the AI age:

```
Prompt/Requirements ─→ Blueprint/Intent ─→ Logic Chain/Architecture ─→ Logic Blocks ─→ Code Blocks/cpp ─→ Code/asm
                        ↑  Human-readable      Human-readable         Human-readable       Auditable    Derived artifacts
                        └────────── Human Input Layer ──────────────────────────────┘
                                         ↓
                               AI is the "Compiler"
                                         ↓
                     One-way generation, no reverse modification
```

**Core Principle**: Upper layers are the **source of truth**; lower layers are **derived artifacts**. When you need to make changes, edit the upper IR and recompile—don't directly modify the generated code.

Just as you wouldn't patch a `.o` file and expect the `.c` file to automatically update—AI shouldn't directly modify code. Instead, modify the upper-layer IR, then `make` again.

---

## 🎯 Core Philosophy

### The Layered Compilation Model

SVP transforms software engineering from "writing code directly" to "designing at abstraction layers, compiled by AI":

```
┌─────────────────────────────────────────────────────────────────────────┐
│                      Human Editing Layer (Source of Truth)              │
├─────────────────────────────────────────────────────────────────────────┤
│  L5: Blueprint    │  Intent documents (why)                             │
│  L4: Logic Chain  │  Program flowcharts/architecture diagrams (what)    │
│  L3: Logic Block  │  Pseudocode/contracts (how)                         │
├─────────────────────────────────────────────────────────────────────────┤
│                        SVP Compilation Pipeline (One-way)               │
├─────────────────────────────────────────────────────────────────────────┤
│  L2: Code Block   │  AI-generated code templates (impl skeleton)        │
│  L1: Code         │  Actual runnable code (full implementation)         │
└─────────────────────────────────────────────────────────────────────────┘

Principles:
1. Upper layers are source data, lower layers are derived artifacts—like .c → .o → binary
2. Humans edit only L5-L3, AI compiles to L2-L1
3. Want to change code? Edit the upper-layer IR and recompile—never directly modify L1
```

```
Intent (L5) → Architecture (L4) → Logic (L3) → Skeleton (L2) → Implementation (L1)
     ↑                                                                       ↓
  Humans design                                                          AI compiles
```

**Key Principles**:
- Humans edit only **L5-L3** (Intent, Architecture, Logic)
- AI compiles **L3 → L1** (Runnable code)
- **Recompile over modify** — Changes in upper layers trigger regeneration of lower layers

---

## 📦 Core Repositories

| Repository | Description | Status |
|------------|-------------|--------|
| [`design`](https://github.com/SemanticVoxelProtocol/design) | Architecture design documents | 📝 In Progress |
| [`svp-spec`](https://github.com/SemanticVoxelProtocol/svp-spec) | Protocol specification (IR definitions) | 📝 In Progress |
| [`svp-ir`](https://github.com/SemanticVoxelProtocol/svp-ir) | TypeScript type definitions | 📝 In Progress |
| [`svp-core`](https://github.com/SemanticVoxelProtocol/svp-core) | Core compilation engine | 📝 In Progress |
| [`svp-cli`](https://github.com/SemanticVoxelProtocol/svp-cli) | Command-line interface | 📝 In Progress |
| [`svp-mcp`](https://github.com/SemanticVoxelProtocol/svp-mcp) | MCP Server (AI integration) | 📝 In Progress |
| [`template-ts`](https://github.com/SemanticVoxelProtocol/template-ts) | TypeScript project template | 📝 In Progress |

---

## 🚀 Quick Start

```bash
# 1. Install CLI
npm install -g @semanticvoxelprotocol/cli

# 2. Create a project
mkdir my-project && cd my-project
svp init

# 3. Define your intent
vim blueprint.svp.yaml

# 4. Compile (using AI)
svp compile --level 5 --ai
svp compile --level 4 --ai
svp compile --level 3 --ai
svp build

# 5. Run
npm run build
npm start
```

---

## 🏗️ Five-Layer Architecture

| Layer | Name | Edited By | Content |
|-------|------|-----------|---------|
| **L5** | Blueprint | Humans | Project intent, domain boundaries, constraints |
| **L4** | Logic Chain | Human-reviewed | Business processes, module interfaces |
| **L3** | Logic Block | Human-reviewed | Pseudocode, contracts, algorithms |
| **L2** | Code Block | AI-generated | Code skeletons, placeholders |
| **L1** | Code | AI-generated | Full runnable code |

**The Golden Rule**: Edit L3 → Recompile → New code. **Never directly modify L1.**

---

## 🤝 Contributing

We're building the future of AI-Human collaboration. Join us if you:

- Believe in "intent-based programming"
- Want AI to work at the right abstraction level
- Are interested in layered compilation models

### How to Participate

1. **Discuss Design** → Open an issue in the `design` repository
2. **Contribute Code** → Look for tasks labeled `good-first-issue`
3. **Share Ideas** → Join [Discussions](https://github.com/orgs/SemanticVoxelProtocol/discussions)

---

## 📖 Learn More

- [Design Philosophy](https://github.com/SemanticVoxelProtocol/design/blob/main/01_Philosophy.md) — Why SVP is needed
- [Architecture Design](https://github.com/SemanticVoxelProtocol/design/blob/main/02_Architecture.md) — Five-layer architecture details
- [MVP Roadmap](https://github.com/SemanticVoxelProtocol/design/blob/main/03_MVP.md) — Implementation planning

---

## 🔮 Vision

> **Make AI a compiler, not an editor.**

Humans define problems, design architecture, and establish contracts. AI compiles designs into code.

---

*Semantic Voxel Protocol — Redefining software engineering for the AI era*
