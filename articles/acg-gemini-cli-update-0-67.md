---
title: "Gemini CLI v0.67 で models コマンドが追加され Claude のフック移行の単位が直った"
emoji: "♊"
type: "tech"
topics: ["geminicli", "hooks"]
published: true
---

Gemini CLI の v0.67.0 は 27 件の変更のうち、新機能が 2 件、修正が 22 件です。

このうち 1 件は、**Claude Code と Gemini CLI を併用している人に実害があった修正**です。Claude のフック設定を移行すると、タイムアウトが 1000 分の 1 になっていました。

> **要点**
> この記事で分かること
>
> - `models` コマンドと `--list-models` でモデルを一覧できるようになったこと
> - Claude のフックの `timeout` が秒、Gemini のそれがミリ秒であること
> - IDE 連携がコンテナのサンドボックス内でも使えるようになったこと

## まとめ

- v0.67.0 は 27 件のうち新機能 2 件、修正 22 件
- `models` コマンドと `--list-models` でモデルを一覧できる。ただし公式ドキュメントには未記載
- Claude のフックを移行するとタイムアウトが 1000 分の 1 になっていた。Claude は秒、Gemini はミリ秒
- 環境変数も `CLAUDE_PROJECT_DIR` ではなく `GEMINI_PROJECT_DIR` に書き換える必要がある
- IDE コンパニオンがコンテナのサンドボックス内でも使えるようになった

---

設定例・手順の全文はこちらで公開しています: [Gemini CLI v0.67 で models コマンドが追加され Claude のフック移行の単位が直った](https://aicoding-guide.com/posts/gemini-cli-update-0-67/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
