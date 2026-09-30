---
title: "Codex は既定で API キーもコマンドに渡す:shell_environment_policy で止める"
emoji: "🧭"
type: "tech"
topics: ["codex", "configtoml", "shellenvironmentpolicy"]
published: false
---

Codex がテストやビルドのコマンドを実行するとき、あなたのシェルにある環境変数はどこまでコマンド側に引き継がれるのでしょうか。`AWS_SECRET_ACCESS_KEY` や `OPENAI_API_KEY` がそのまま渡っていれば、Codex が生成したコマンドがそれらを読める状態です。

結論として、引き継ぎの範囲は `config.toml` の `[shell_environment_policy]` で決まります。`inherit` で土台を選び、`ignore_default_excludes = false` で KEY/SECRET/TOKEN を含む変数を落とし、`filters` と `set` で細かく調整します。

> **要点**
> この記事で分かること
>
> - `inherit` の 3 つの値(`all` / `core` / `none`)と既定
> - KEY / SECRET / TOKEN を含む変数が既定でどう扱われるか
> - `filters`、`set`、旧形式の `exclude` / `include_only` の書き方と適用順序

## まとめ

- 既定は `inherit = "all"` かつ `ignore_default_excludes = true` で、KEY / SECRET / TOKEN を含む変数もコマンドに渡る
- `ignore_default_excludes = false` にすると、それらの名前の変数が自動で除外される
- 名前で判別できない秘密情報は `[shell_environment_policy.filters]` で `"パターン" = "exclude"` と書く
- `inherit = "core"` / `"none"` と `set` で「必要な変数だけ渡す」構成にできる
- 適用順序は 自動除外 → 明示除外 → `set` → include 許可。MCP サーバーの env は別設定

---

設定例・手順の全文はこちらで公開しています: [Codex は既定で API キーもコマンドに渡す:shell_environment_policy で止める](https://aicoding-guide.com/posts/codex-shell-environment-policy/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
