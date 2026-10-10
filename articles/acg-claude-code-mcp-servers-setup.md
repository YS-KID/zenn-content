---
title: "Claude Code に MCP サーバーを追加する方法、claude mcp add・.mcp.json・スコープ・環境変数の渡し方"
emoji: "🤖"
type: "tech"
topics: ["claudecode", "mcp", "mcpjson", "scope"]
published: false
---

MCP(Model Context Protocol)は、AI エージェントに外部ツールやデータソースを接続するための共通規格です。Claude Code に MCP サーバーを追加すると、GitHub の Issue 操作、ブラウザ操作、データベース参照などを、Claude が自分で判断して実行できるようになります。

この記事では、`claude mcp add` コマンドによる追加手順、設定を「自分だけ」「このプロジェクトのチーム全員」「自分の全プロジェクト」のどこに置くかを決めるスコープ、チームで共有する `.mcp.json` にトークンを書かずに環境変数から渡す書き方、接続確認と権限設定までを順に整理します。

> **要点**
> この記事で分かること
>
> - `claude mcp add` の基本形と stdio / HTTP の違い
> - local / project / user の 3 つのスコープの保存先・共有範囲・優先順位
> - `.mcp.json` の書き方と、`${VAR}` で環境変数からトークンを渡す方法
> - project スコープの承認プロンプトと、接続確認・権限設定の手順

## まとめ

- `claude mcp add 名前 -- 起動コマンド` で stdio サーバー、`--transport http` でリモートサーバーを追加する
- スコープは local(既定、そのプロジェクトで自分だけ)/ project(`.mcp.json` でチーム共有)/ user(自分の全プロジェクト)。同じ名前は local → project → user の順で 1 つだけ使われる
- `.mcp.json` ではトークンを `${GITHUB_TOKEN}` の形で環境変数から読ませ、値は書かない。`${VAR:-既定値}` で既定値を指定でき、env・args・url・headers で使える
- project スコープのサーバーは対話セッションで承認が必要。やり直しは `claude mcp reset-project-choices`
- `/mcp` と `claude mcp list` で接続状態を確認し、permissions で自動許可の範囲を決める

---

設定例・手順の全文はこちらで公開しています: [Claude Code に MCP サーバーを追加する方法、claude mcp add・.mcp.json・スコープ・環境変数の渡し方](https://aicoding-guide.com/posts/claude-code-mcp-servers-setup/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
