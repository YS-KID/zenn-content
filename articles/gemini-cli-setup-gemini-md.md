---
title: "Gemini CLI のインストールと GEMINI.md の書き方:Google アカウントで無料で始める"
emoji: "♊"
type: "tech"
topics: ["geminicli", "geminimd"]
published: false
---

Gemini CLI は Google が公開しているオープンソースのターミナル向けコーディングエージェントです。最大の特徴は、個人の Google アカウントでログインするだけで、上限付きながら無料で使い始められることです。

この記事では、インストールからログイン、最初のタスクまでの手順と、プロジェクトのルールを伝えるための **GEMINI.md** の書き方をまとめます。

> **要点**
> この記事で分かること
>
> - インストールと Google アカウント / API キーでのログイン
> - GEMINI.md の配置場所、読み込みの仕組み、確認コマンド
> - そのまま使える GEMINI.md のテンプレート

## まとめ

- `npm install -g @google/gemini-cli` で入れ、`gemini` を起動して Google アカウントでログインする
- GEMINI.md は `~/.gemini/`、リポジトリのルート、サブディレクトリの 3 階層で結合される
- `/memory show` で読み込み状況を確認し、`/memory refresh` で再読み込みする
- `/init` で雛形を作り、コマンド・規約・変更禁止・進め方の 4 種類に絞る

---

設定例・手順の全文はこちらで公開しています: [Gemini CLI のインストールと GEMINI.md の書き方:Google アカウントで無料で始める](https://aicoding-guide.com/posts/gemini-cli-setup-gemini-md/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
