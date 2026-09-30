---
title: "Claude Code に MCP サーバーを追加する方法(claude mcp add と .mcp.json の使い分け)"
emoji: "🤖"
type: "tech"
topics: ["claudecode", "mcp"]
published: true
---

MCP(Model Context Protocol)は、AI エージェントに外部ツールやデータソースを接続するための共通規格です。Claude Code に MCP サーバーを追加すると、GitHub の Issue 操作、ブラウザ操作、データベース参照などを、Claude が自分で判断して実行できるようになります。

この記事では、`claude mcp add` コマンドによる追加手順と、設定を「自分だけ」「このプロジェクトのチーム全員」「自分の全プロジェクト」のどこに置くかを決めるスコープの考え方を整理します。

> **要点**
> この記事で分かること
>
> - `claude mcp add` の基本形と stdio / HTTP の違い
> - local / project / user の 3 つのスコープと保存先
> - 接続確認、認証、権限設定の方法

## まとめ

- `claude mcp add 名前 -- 起動コマンド` で stdio サーバー、`--transport http` でリモートサーバーを追加する
- スコープは local(自分のみ)/ project(`.mcp.json` でチーム共有)/ user(自分の全プロジェクト)
- トークンは `${VAR}` で環境変数から読ませ、`.mcp.json` に直接書かない
- `/mcp` と `claude mcp list` で接続状態を確認し、permissions で自動許可の範囲を決める

---

設定例・手順の全文はこちらで公開しています: [Claude Code に MCP サーバーを追加する方法(claude mcp add と .mcp.json の使い分け)](https://aicoding-guide.com/posts/claude-code-mcp-servers-setup/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
