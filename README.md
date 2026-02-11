# Spec-Driven Development Template

スペック駆動開発のためのプロジェクトテンプレートです。Next.js + TypeScript + Tailwind CSS をベースに、Claude Code のスキル・コマンドを活用した体系的な開発フローを提供します。

## 技術スタック

- Next.js (App Router) + TypeScript
- Tailwind CSS
- Vitest + React Testing Library
- ESLint + Prettier
- Husky + lint-staged

## プロジェクト構造

```
.claude/                 # Claude Code 設定
  commands/              # /setup-project, /add-feature, /review-docs
  skills/                # ドキュメント作成・管理用スキル（7種）
  agents/                # レビュー用サブエージェント（2種）
docs/
  ideas/                 # アイデア・下書き（自由形式）
  product-requirements.md  # ← /setup-project で自動生成
  functional-design.md
  architecture.md
  repository-structure.md
  development-guidelines.md
  glossary.md
.steering/               # 作業単位のドキュメント（ローカルのみ、gitignore済み）
app/                     # Next.js App Router
CLAUDE.md                # プロジェクトメモリ
```

## 使い方

### 1. セットアップ

```bash
npm install
```

Dev Container を利用する場合は、VS Code で「Reopen in Container」を選択してください（Docker が必要です）。

### 2. アイデアファイルの配置

`docs/ideas/` にプロダクトのアイデアや要件をマークダウンで配置します。

```bash
# 例
docs/ideas/my-product-idea.md
```

形式は自由です。壁打ちやブレストの成果物をそのまま置いてください。

### 3. プロジェクトの初期化

Claude Code で以下を実行すると、アイデアファイルをもとに6つの永続ドキュメントが対話的に作成されます。

```
/setup-project
```

### 4. 機能の実装

```
/add-feature [機能名]
```

ドキュメントに基づいて、計画 → 実装 → テスト → 検証が可能な限り自動で実行されます。解決困難な問題が発生した場合はユーザーに確認を求めます。

### 5. ドキュメントのレビュー

```
/review-docs docs/product-requirements.md
```

## 開発コマンド

```bash
npm run dev          # 開発サーバー起動
npm run build        # プロダクションビルド
npm run start        # プロダクションサーバー起動
npm run typecheck    # 型チェック
npm run lint         # リント
npm run test         # テスト実行
npm run test:watch   # テスト（ウォッチモード）
npm run test:coverage # カバレッジ付きテスト
```

## ライセンス

MIT
