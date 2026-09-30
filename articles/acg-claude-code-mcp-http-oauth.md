---
title: "Claude Code でリモート MCP サーバーに OAuth ログインする手順:/mcp と claude mcp login"
emoji: "🤖"
type: "tech"
topics: ["claudecode", "mcp", "oauth"]
published: false
---

Sentry や Linear、Notion のようなホスト型の MCP サーバーは、URL を登録しただけでは使えません。ブラウザでのサインインが要ります。`claude mcp list` に `! Needs authentication` と出るのがその状態です。

結論として、`claude mcp add --transport http <名前> <URL>` で追加したあと、セッション内で `/mcp` を開いてサーバーを選び `Authenticate` を実行するか、シェルから `claude mcp login <名前>` を実行します。トークンは安全に保存され、自動で更新されます。

この記事はシリーズの一部です。サーバーの追加方法全体は [Claude Code に MCP サーバーを追加する方法](https://aicoding-guide.com/posts/claude-code-mcp-servers-setup/) を参照してください。

> **要点**
> この記事で分かること
>
> - `/mcp` と `claude mcp login` の 2 つのサインイン方法
> - コールバックポートを固定する `--callback-port` と、事前登録した client ID の渡し方
> - トークンが切れたとき、ブラウザが開かないときの対処

## まとめ

- `claude mcp add --transport http <名前> <URL>` で追加し、`/mcp` の `Authenticate` かシェルの `claude mcp login <名前>` でサインインする
- `claude mcp logout <名前>` と `/mcp` の「Clear authentication」で認証を取り消せる
- ブラウザのない環境では `claude mcp login --no-browser` で URL を表示し、リダイレクト URL を貼り戻す
- 動的クライアント登録に非対応なら `--client-id` と `--callback-port`、必要なら `--client-secret` を使う
- トークンが拒否されたら `/mcp` の **Re-authenticate**。スコープ不足は `oauth.scopes` に足してからサインインし直す

---

設定例・手順の全文はこちらで公開しています: [Claude Code でリモート MCP サーバーに OAuth ログインする手順:/mcp と claude mcp login](https://aicoding-guide.com/posts/claude-code-mcp-http-oauth/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
