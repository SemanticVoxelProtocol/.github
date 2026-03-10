# Semantic Voxel Protocol (SVP)

**AI と人間の協働プログラミングのための認知インフラストラクチャ**

---

<div align="center">

**[English](./README_EN.md) | 日本語 | [中文](./README.md)**

</div>

---

## Why SVP?

現在の AI コーディングツール（Cursor、Claude Code、GitHub Copilot）は**テキスト/コードレベル**で動作しており、以下の問題を引き起こしています：

- **コンテキストオーバーフロー**: 大規模コードベースで AI が機能不全に陥る
- **破壊的編集**: AI の「修正」が人間の論理を破壊する
- **アーキテクチャの漂流**: システム構造に意味的なガードレールがない
- **レビューの悪夢**: 人間が数千行の生成コードを監査する必要がある

**根本原因**: AI が誤った抽象化レイヤーで作業しているからです。

> 人間が機械語を書かないように、AI もソースコードを直接操作すべきではありません。

SVP は**レイヤードコンパイル**を導入します—AI 時代に適応した古典的なソフトウェアエンジニアリングのアプローチです：

```
意図 (L5) → アーキテクチャ (L4) → ロジック (L3) → スケルトン (L2) → コード (L1)
    ↑                                                              ↓
 人間が設計                                                    AI がコンパイル
```

**核心原則**: 上位レイヤーは**真の情報源**、下位レイヤーは**派生アーティファクト**です。変更が必要な場合は、生成されたコードではなく上位レイヤーを編集して再コンパイルします。

---

## 🎯 核心理念

### レイヤードコンパイルモデル

SVP はソフトウェアエンジニアリングを「直接コードを書く」から「抽象レイヤーで設計し、AI によってコンパイルされる」へと変換します：

```
意図 (L5) → アーキテクチャ (L4) → ロジック (L3) → スケルトン (L2) → 実装 (L1)
    ↑                                                                       ↓
 人間が設計                                                             AI がコンパイル
```

**核心原則**:
- 人間は **L5-L3** のみを編集（意図、アーキテクチャ、ロジック）
- AI が **L3 → L1** をコンパイル（実行可能なコード）
- **再コンパイルは修正より優位** — 上位レイヤーの変更が下位レイヤーの再生成をトリガー

---

## 📦 コアリポジトリ

| リポジトリ | 説明 | ステータス |
|------------|------|------------|
| [`design`](https://github.com/SemanticVoxelProtocol/design) | アーキテクチャ設計ドキュメント | 📝 進行中 |
| [`svp-spec`](https://github.com/SemanticVoxelProtocol/svp-spec) | プロトコル仕様（IR 定義） | 📝 進行中 |
| [`svp-ir`](https://github.com/SemanticVoxelProtocol/svp-ir) | TypeScript 型定義 | 📝 進行中 |
| [`svp-core`](https://github.com/SemanticVoxelProtocol/svp-core) | コアコンパイルエンジン | 📝 進行中 |
| [`svp-cli`](https://github.com/SemanticVoxelProtocol/svp-cli) | コマンドラインインターフェース | 📝 進行中 |
| [`svp-mcp`](https://github.com/SemanticVoxelProtocol/svp-mcp) | MCP Server（AI 統合） | 📝 進行中 |
| [`template-ts`](https://github.com/SemanticVoxelProtocol/template-ts) | TypeScript プロジェクトテンプレート | 📝 進行中 |

---

## 🚀 クイックスタート

```bash
# 1. CLI をインストール
npm install -g @semanticvoxelprotocol/cli

# 2. プロジェクトを作成
mkdir my-project && cd my-project
svp init

# 3. 意図を定義
vim blueprint.svp.yaml

# 4. コンパイル（AI を使用）
svp compile --level 5 --ai
svp compile --level 4 --ai
svp compile --level 3 --ai
svp build

# 5. 実行
npm run build
npm start
```

---

## 🏗️ 5 レイヤーアーキテクチャ

| レイヤー | 名前 | 編集者 | 内容 |
|----------|------|--------|------|
| **L5** | Blueprint | 人間 | プロジェクト意図、ドメイン境界、制約 |
| **L4** | Logic Chain | 人間レビュー | ビジネスプロセス、モジュールインターフェース |
| **L3** | Logic Block | 人間レビュー | 疑似コード、契約、アルゴリズム |
| **L2** | Code Block | AI 生成 | コードスケルトン、プレースホルダー |
| **L1** | Code | AI 生成 | 完全な実行可能コード |

**黄金律**: L3 を編集 → 再コンパイル → 新しいコード。**L1 を直接変更しない。**

---

## 🤝 コントリビューション

AI と人間の協働の未来を構築しています。以下の方はぜひご参加ください：

- 「意図ベースプログラミング」を信じている方
- AI が正しい抽象化レベルで作業することを望む方
- レイヤードコンパイルモデルに興味がある方

### 参加方法

1. **設計を議論** → `design` リポジトリで Issue を開く
2. **コードを貢献** → `good-first-issue` ラベルのタスクを探す
3. **アイデアを共有** → [Discussions](https://github.com/orgs/SemanticVoxelProtocol/discussions) に参加

---

## 📖 詳細情報

- [設計哲学](https://github.com/SemanticVoxelProtocol/design/blob/main/01_Philosophy.md) — SVP が必要な理由
- [アーキテクチャ設計](https://github.com/SemanticVoxelProtocol/design/blob/main/02_Architecture.md) — 5 レイヤーアーキテクチャの詳細
- [MVP ロードマップ](https://github.com/SemanticVoxelProtocol/design/blob/main/03_MVP.md) — 実装計画

---

## 🔮 ビジョン

> **AI をエディタではなく、コンパイラにする。**

人間が問題を定義し、アーキテクチャを設計し、契約を確立する。AI が設計をコードにコンパイルする。

---

*Semantic Voxel Protocol — AI 時代のソフトウェアエンジニアリングを再定義する*
