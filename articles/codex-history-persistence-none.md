---
title: "Codex の会話履歴をディスクに残さない history.persistence と、認証情報の保存先の設定"
emoji: "🧭"
type: "tech"
topics: ["codex", "configtoml", "history"]
published: true
---

共有マシンや検証用の環境で Codex を使うとき、「会話の内容をディスクに残したくない」「ログイン情報をファイルに書きたくない」という要件が出ます。Codex CLI にはそれぞれに対応する設定があります。

結論として、会話履歴は `[history]` の `persistence = "none"` で保存を止められ、`max_bytes` で上限を付けられます。認証情報の保存先は `cli_auth_credentials_store` で `file` / `keyring` / `ephemeral` から選べます。

> **要点**
> この記事で分かること
>
> - `history.persistence` の 2 つの値と既定、`max_bytes` の動き
> - 認証情報の保存先を決める `cli_auth_credentials_store` の 4 つの値
> - 「残さない」設定にしたときに失うもの

## まとめ

- `[history] persistence = "none"` で会話履歴をディスクに保存しない。既定は `save-all`
- 容量だけ抑えるなら `max_bytes`。超えたら古いエントリから削除される
- 認証情報の保存先は `cli_auth_credentials_store`(`auto` / `file` / `keyring` / `ephemeral`)
- `none` や `ephemeral` にすると再開や自動ログインができなくなる
- ローカル保存の設定と、OpenAI へのデータ送信(analytics / feedback / otel)は別のキー

---

設定例・手順の全文はこちらで公開しています: [Codex の会話履歴をディスクに残さない history.persistence と、認証情報の保存先の設定](https://aicoding-guide.com/posts/codex-history-persistence-none/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
