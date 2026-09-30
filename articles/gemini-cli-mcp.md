---
title: "Gemini CLI に MCP サーバーを追加する:settings.json の mcpServers の書き方と接続確認"
emoji: "♊"
type: "tech"
topics: ["geminicli", "mcp", "settingsjson"]
published: false
---

Gemini CLI も MCP(Model Context Protocol)に対応しており、ブラウザ操作やドキュメント検索などの外部ツールを接続できます。設定は `settings.json` の `mcpServers` に書く JSON 形式で、Claude Code の `.mcp.json` とほぼ同じ構造です。

この記事では、設定ファイルの場所と書き方、接続確認、ツールの許可設定、動かないときの切り分けをまとめます。

> **要点**
> この記事で分かること
>
> - `settings.json` の `mcpServers` の書き方と、ユーザー / プロジェクトの使い分け
> - `/mcp` による接続確認と、ツール実行の許可設定
> - 動かないときの切り分け手順

## まとめ

- `~/.gemini/settings.json`(ユーザー)または `.gemini/settings.json`(プロジェクト)の `mcpServers` に書く
- `command` / `args` / `env` は Claude Code の `.mcp.json` と同じ構造。トークンは環境変数から読ませる
- `/mcp` で接続状態、`/tools` でツール一覧を確認する
- `trust` は読み取り専用のサーバーに限定し、書き込み系は確認を残す

---

設定例・手順の全文はこちらで公開しています: [Gemini CLI に MCP サーバーを追加する:settings.json の mcpServers の書き方と接続確認](https://aicoding-guide.com/posts/gemini-cli-mcp/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
