# Semantic Voxel Protocol (SVP)

**AI-Human 协作编程的认知基础设施**

---

## 🎯 核心理念

> 就像我们人类写程序时不管机器码一样，AI 不应该直接操作代码。

SVP 将软件工程从"直接写代码"转变为"在抽象层设计，由 AI 编译实现"：

```
意图 (L5) → 架构 (L4) → 逻辑 (L3) → 代码骨架 (L2) → 实现 (L1)
  ↑                                                      ↓
人类设计                                              AI 编译
```

**核心原则**：
- 人类只在 **L5-L3** 层编辑（意图、架构、逻辑）
- AI 负责将 **L3 编译为 L1**（可运行代码）
- **重新编译优于修改** —— 上层变更触发下层重新生成

---

## 📦 核心仓库

| 仓库 | 描述 | 状态 |
|------|------|------|
| [`design`](https://github.com/SemanticVoxelProtocol/design) | 架构设计文档 | 📝 进行中 |
| [`svp-spec`](https://github.com/SemanticVoxelProtocol/svp-spec) | 协议规范 (IR 定义) | 📝 进行中 |
| [`svp-ir`](https://github.com/SemanticVoxelProtocol/svp-ir) | TypeScript 类型定义 | 📝 进行中 |
| [`svp-core`](https://github.com/SemanticVoxelProtocol/svp-core) | 核心编译引擎 | 📝 进行中 |
| [`svp-cli`](https://github.com/SemanticVoxelProtocol/svp-cli) | 命令行工具 | 📝 进行中 |
| [`svp-mcp`](https://github.com/SemanticVoxelProtocol/svp-mcp) | MCP Server (AI 集成) | 📝 进行中 |
| [`template-ts`](https://github.com/SemanticVoxelProtocol/template-ts) | TypeScript 项目模板 | 📝 进行中 |

---

## 🚀 快速开始

```bash
# 1. 安装 CLI
npm install -g @semanticvoxelprotocol/cli

# 2. 创建项目
mkdir my-project && cd my-project
svp init

# 3. 定义意图
vim blueprint.svp.yaml

# 4. 编译（使用 AI）
svp compile --level 5 --ai
svp compile --level 4 --ai
svp compile --level 3 --ai
svp build

# 5. 运行
npm run build
npm start
```

---

## 🏗️ 五层架构

| 层级 | 名称 | 谁编辑 | 内容 |
|------|------|--------|------|
| **L5** | Blueprint | 人类 | 项目意图、领域划分、约束 |
| **L4** | Logic Chain | 人类审核 | 业务流程、模块接口 |
| **L3** | Logic Block | 人类审核 | 伪代码、契约、算法 |
| **L2** | Code Block | AI 生成 | 代码骨架、占位符 |
| **L1** | Code | AI 生成 | 完整可运行代码 |

**规则**：修改 L3 → 重新编译 → 新代码。禁止直接改 L1。

---

## 🤝 贡献

我们正在构建 AI-Human 协作的未来。如果你：

- 认同"意图编程"的理念
- 希望 AI 在正确的抽象层工作
- 对分层编译模型感兴趣

欢迎加入！

### 参与方式

1. **讨论设计** → 在 `design` 仓库开 Issue
2. **贡献代码** → 查看带有 `good-first-issue` 标签的任务
3. **分享想法** → 加入 [Discussions](https://github.com/orgs/SemanticVoxelProtocol/discussions)

---

## 📖 了解更多

- [设计哲学](https://github.com/SemanticVoxelProtocol/design/blob/main/01_Philosophy.md) —— 为什么需要 SVP
- [架构设计](https://github.com/SemanticVoxelProtocol/design/blob/main/02_Architecture.md) —— 五层架构详解
- [MVP 路线图](https://github.com/SemanticVoxelProtocol/design/blob/main/03_MVP.md) —— 实现规划

---

## 🔮 愿景

> **让 AI 成为编译器，而非编辑器。**

人类定义问题、设计架构、确立契约。AI 负责将设计编译为代码。

---

*Semantic Voxel Protocol —— 为 AI 时代重新定义软件工程*
