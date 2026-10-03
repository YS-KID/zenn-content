---
title: "MCP のツールを permissions で自動許可する書き方:mcp__ 記法とワイルドカードの制限"
emoji: "🤖"
type: "tech"
topics: ["claudecode", "mcp", "permissions", "settingsjson"]
published: true
---

MCP サーバーを追加すると、そのツールを呼ぶたびに確認を求められます。読み取り専用のツールまで毎回止まるのは手間です。

結論として、`settings.json` の `permissions.allow` に `mcp__<サーバー名>` と書けばそのサーバーのツール全体を、`mcp__<サーバー名>__<ツール名>` と書けば個別のツールを自動許可できます。ただし **allow のワイルドカードには `mcp__<サーバー名>__` という前置きが必須** で、`mcp__*` のような書き方は読み飛ばされます。

サーバーの追加方法そのものは [Claude Code に MCP サーバーを追加する方法](https://aicoding-guide.com/posts/claude-code-mcp-servers-setup/) を参照してください。

> **要点**
> この記事で分かること
>
> - サーバー単位・ワイルドカード・ツール単位の 3 つの書き方
> - allow のワイルドカードに前置きが要る理由と、deny・ask との違い
> - 括弧付きの `mcp__` ルールが読み飛ばされること

## まとめ

- `allow` に `mcp__<サーバー名>` でサーバー全体、`mcp__<サーバー名>__<ツール名>` で個別のツールを自動許可する
- allow のワイルドカードは `mcp__<サーバー名>__` の後ろだけ。`mcp__*` や `*` は警告付きで読み飛ばされる
- deny と ask はツール名全体のワイルドカードを使える。`deny` の `mcp__*` で全 MCP ツールを禁止できる
- 評価順は deny → ask → allow。具体性に関係なく、最初に一致したものが決まる
- 括弧付きの `mcp__` ルールは設定ファイルから読み飛ばされる。パラメータで絞るなら `--disallowedTools`

---

設定例・手順の全文はこちらで公開しています: [MCP のツールを permissions で自動許可する書き方:mcp__ 記法とワイルドカードの制限](https://aicoding-guide.com/posts/claude-code-mcp-allow-tools/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
