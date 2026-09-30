---
title: "Codex CLI のセットアップと AGENTS.md の書き方【ChatGPT アカウントで始める】"
emoji: "🧭"
type: "tech"
topics: ["codex", "codexcli", "agentsmd"]
published: true
---

Codex CLI は OpenAI が提供するターミナル向けのコーディングエージェントです。ChatGPT のアカウントでログインでき、ローカルのリポジトリを読んでコードを書き、コマンドを実行します。

この記事では、インストールからログイン、最初のタスク実行までの手順と、Codex がプロジェクトのルールを理解するために読み込む **AGENTS.md** の書き方をまとめます。

> **要点**
> この記事で分かること
>
> - Codex CLI のインストールと ChatGPT アカウント / API キーでのログイン
> - AGENTS.md の配置場所と読み込みの優先順位
> - そのまま使える AGENTS.md のテンプレート

## まとめ

- `npm install -g @openai/codex` または Homebrew で入れ、`codex` で起動して ChatGPT アカウントか API キーでログインする
- `OPENAI_API_KEY` が設定されていると API キーが優先されるので注意する
- AGENTS.md は `~/.codex/`、リポジトリのルート、サブディレクトリの 3 階層で、深いものが優先される
- `/init` で雛形を作り、「見ただけでは分からない約束事」だけを残す

---

設定例・手順の全文はこちらで公開しています: [Codex CLI のセットアップと AGENTS.md の書き方【ChatGPT アカウントで始める】](https://aicoding-guide.com/posts/codex-cli-setup-agents-md/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
