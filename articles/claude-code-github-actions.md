---
title: "GitHub Actions で Claude Code を動かす:claude-code-action の導入と使い方"
emoji: "🤖"
type: "tech"
topics: ["claudecode", "githubactions", "ci"]
published: false
---

Issue に「@claude この不具合を直して」とコメントすると、Claude Code が修正を実装して PR を作る。PR が開かれると自動でレビューコメントが付く。こうした仕組みは、公式の **claude-code-action** を使うと 1 つのワークフローファイルで実現できます。

この記事では、セットアップから、メンション応答と自動レビューの 2 つの構成、権限とコストを絞る方法までを扱います。

> **要点**
> この記事で分かること
>
> - `/install-github-app` によるセットアップと API キーの登録
> - `@claude` メンションに応答するワークフロー
> - PR 作成時に自動レビューするワークフローと、権限・コストの制御

## まとめ

- `/install-github-app` で GitHub App とワークフローを導入し、`ANTHROPIC_API_KEY` を Secrets に登録する
- `@claude` メンション応答と、PR 自動レビューの 2 構成が基本
- `if:` でコメント投稿者を制限し、`--max-turns` と Sonnet 系モデルで費用を抑える
- レビュー基準や禁止事項はワークフローではなく CLAUDE.md に書く

---

設定例・手順の全文はこちらで公開しています: [GitHub Actions で Claude Code を動かす:claude-code-action の導入と使い方](https://aicoding-guide.com/posts/claude-code-github-actions/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
