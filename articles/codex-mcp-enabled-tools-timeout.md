---
title: "Codex で MCP サーバーの一部のツールだけ許可する enabled_tools と、タイムアウト・承認の設定"
emoji: "🧭"
type: "tech"
topics: ["codex", "mcp", "configtoml", "enabledtools", "tooltimeoutsec"]
published: false
---

MCP サーバーを追加すると、そのサーバーが公開するツールが全部 Codex から使えるようになります。ブラウザ操作のサーバーで「スクリーンショットは撮ってほしいがフォーム送信はさせたくない」のように、一部だけを許可したい場面はよくあります。

結論として、`[mcp_servers.<id>]` の `enabled_tools` と `disabled_tools` でツールを絞り、`default_tools_approval_mode` や `tools.<tool>.approval_mode` で実行前の承認を要求できます。起動やツール実行の待ち時間は `startup_timeout_sec` と `tool_timeout_sec` で調整します。

> **要点**
> この記事で分かること
>
> - ツールの許可リスト / 拒否リストの書き方
> - 起動タイムアウトとツール実行タイムアウトの既定値と変え方
> - 承認モードと、出力トークンの上限

## まとめ

- `enabled_tools` / `disabled_tools` でサーバーごとに使えるツールを絞れる
- 起動は `startup_timeout_sec`(既定 10 秒)、実行は `tool_timeout_sec`(既定 60 秒)。起動できないと困るサーバーは `required = true`
- `default_tools_approval_mode` と `tools.<tool>.approval_mode` で実行前の承認を要求できる
- `output_token_limit` でツールごとの出力トークンを制限できる
- トークンは `bearer_token_env_var` や `env_vars` で環境変数から渡し、値を直接書かない

---

設定例・手順の全文はこちらで公開しています: [Codex で MCP サーバーの一部のツールだけ許可する enabled_tools と、タイムアウト・承認の設定](https://aicoding-guide.com/posts/codex-mcp-enabled-tools-timeout/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
