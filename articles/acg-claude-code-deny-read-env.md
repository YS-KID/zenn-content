---
title: "Claude Code で .env を読ませない deny 設定(Read ルールの書き方)"
emoji: "🤖"
type: "tech"
topics: ["claudecode", "env", "deny", "permissions"]
published: false
---

`.env` には API キーやデータベースのパスワードが入っています。Claude Code はワーキングディレクトリ内のファイル読み取りを確認なしで実行するため、放っておくと `.env` の中身がそのままモデルへの入力に含まれます。

これを止める確実な方法は、`settings.json` の `permissions.deny` に `Read` ルールを書くことです。deny ルールは allow より先に評価され、権限モードに関係なくブロックされます。

> **要点**
> この記事で分かること
>
> - `.env` を読ませない deny ルールの書き方
> - パターンの書き方によって適用範囲がどう変わるか
> - deny が効かないケースと、その場合の対処

## まとめ

- `.claude/settings.json` の `permissions.deny` に `Read(./.env)` と `Read(./.env.*)` を書く
- `Read` の deny は Edit と Write にも効くが、NotebookEdit は対象外
- `Read(./.env)` はカレントディレクトリのみ、`Read(.env)` は任意の深さに一致する
- deny は allow より優先され、bypassPermissions を含むすべてのモードで効く
- スクリプトが内部で開くファイルには効かないため、確実に遮断するならサンドボックスを使う

---

設定例・手順の全文はこちらで公開しています: [Claude Code で .env を読ませない deny 設定(Read ルールの書き方)](https://aicoding-guide.com/posts/claude-code-deny-read-env/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
