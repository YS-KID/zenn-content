---
title: ".mcp.json で環境変数からトークンを渡す書き方(${VAR} 展開)"
emoji: "🤖"
type: "tech"
topics: ["claudecode", "mcpjson", "mcp"]
published: false
---

`.mcp.json` はチームで共有するために Git にコミットするファイルです。ここに GitHub のアクセストークンを直接書くと、リポジトリを見られる全員に漏れます。Claude Code は `.mcp.json` の中で `${環境変数名}` の形で環境変数を参照できるので、トークンの実体はシェル側に置きます。

> **要点**
> この記事で分かること
>
> - `${VAR}` と `${VAR:-既定値}` の書き方
> - 展開できる場所(env、args、url など)
> - 環境変数の置き場所と、チームでの運用ルール

## まとめ

- `.mcp.json` では `${GITHUB_TOKEN}` の形で環境変数を参照し、値は書かない
- `${VAR:-既定値}` で未設定時の既定値を指定できる。env、args、url、headers で使える
- 環境変数はシェルの設定ファイルに置き、VS Code から使う場合は再起動して反映する
- 誤ってコミットしたら、まずトークンを失効させる

---

設定例・手順の全文はこちらで公開しています: [.mcp.json で環境変数からトークンを渡す書き方(${VAR} 展開)](https://aicoding-guide.com/posts/claude-code-mcp-json-env/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
