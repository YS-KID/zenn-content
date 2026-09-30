---
title: "Codex CLI に MCP サーバーを設定する:config.toml の書き方と接続確認"
emoji: "🧭"
type: "tech"
topics: ["codex", "codexcli", "mcp", "configtoml"]
published: true
---

MCP(Model Context Protocol)サーバーを Codex CLI に接続すると、ブラウザ操作、ドキュメント検索、Issue 管理などを Codex が自分で判断して実行できるようになります。Codex の MCP 設定は `config.toml` に集約されており、Claude Code や Gemini CLI とは書き方が異なります。

この記事では、config.toml への書き方、コマンドによる追加、接続確認とトラブル時の切り分けをまとめます。

> **要点**
> この記事で分かること
>
> - `[mcp_servers.名前]` セクションの書き方(stdio 方式)
> - 環境変数・トークンの安全な渡し方
> - 接続確認と、動かないときの切り分け手順

## まとめ

- `~/.codex/config.toml` の `[mcp_servers.名前]` に `command` / `args` / `env` を書く
- トークンは環境変数から読ませ、config.toml に直接書かない
- `/mcp` で接続状態を確認し、動かないときはサーバー単体起動 → 環境変数 → TOML 構文の順で切り分ける
- command / args / env の内容は Claude Code や Gemini CLI と共通なので流用できる

---

設定例・手順の全文はこちらで公開しています: [Codex CLI に MCP サーバーを設定する:config.toml の書き方と接続確認](https://aicoding-guide.com/posts/codex-mcp-setup/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
