---
title: "claude mcp add の --scope local / project / user の違いと使い分け"
emoji: "🤖"
type: "tech"
topics: ["claudecode", "mcp", "scope", "mcpjson"]
published: true
---

`claude mcp add` で MCP サーバーを追加するとき、`--scope` に何を指定すべきか迷います。名前から「local はローカル、user はユーザー」と推測はできますが、`local` と `user` はどちらも同じファイルに保存されるため、違いが分かりにくい部分です。

見るべき点は **保存先・共有範囲・優先順位** の 3 つです。結論として、自分だけがそのプロジェクトで使うなら `local`(既定)、チームで共有するなら `project`、自分がすべてのプロジェクトで使うなら `user` です。

> **要点**
> この記事で分かること
>
> - 3 つのスコープの保存先と共有範囲の違い
> - `project` が `.mcp.json` に書かれ、承認プロンプトが出る仕組み
> - 同じ名前が複数のスコープにあるときの優先順位

## まとめ

- `--scope` の既定は `local`。そのプロジェクトで自分だけが使う設定になる
- `local` と `user` はどちらも `~/.claude.json` だが、local はプロジェクトのパスの下に保存される
- `project` はプロジェクト直下の `.mcp.json` に書かれ、バージョン管理でチームに共有される
- `project` のサーバーは対話セッションで承認が必要。やり直しは `claude mcp reset-project-choices`
- 同じ名前が複数あると local → project → user → プラグイン → コネクタの順で 1 つだけ使われる

---

設定例・手順の全文はこちらで公開しています: [claude mcp add の --scope local / project / user の違いと使い分け](https://aicoding-guide.com/posts/claude-code-mcp-scope/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
