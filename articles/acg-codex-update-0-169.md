---
title: "Codex CLI v0.168 と v0.169 の変更点と codex exec の --trust が必要になる場面"
emoji: "🧭"
type: "tech"
topics: ["codex", "codexcli", "codexexec", "trustlevel"]
published: true
---

Codex CLI の v0.168.0 と v0.169.0 で、CI の運用に効く変更が 1 件入りました。**`codex exec` が、信頼していないプロジェクトの設定と MCP サーバーを読まなくなりました。**

このリリースにはもう 1 つ注意点があります。リリースノートに登場する設定キーのうち、**公式の設定リファレンスに載っていないものが 3 つあり、値の一覧が食い違っているものが 1 つあります。** 設定を書く前に、どれが確認済みかを分けておく必要があります。

> **要点**
> この記事で分かること
>
> - `codex exec` の信頼判定が何を無効にするのか、`--trust` をいつ付けるのか
> - プロジェクトの信頼を設定ファイルで指定する `projects.<path>.trust_level`
> - リリースノートの設定キーのうち、設定リファレンスで裏が取れないもの

## まとめ

- `codex exec` は信頼していないディレクトリでプロジェクト設定を読まない。`--sandbox workspace-write` では広がらず、`--trust` を明示する
- 設定ファイルで先に指定するなら `projects.<path>.trust_level` に `"trusted"` を書く。`approval_policy = "untrusted"` とは別物
- `features.tui_workspace`、`features.image_generation_animation`、`incremental_tools_legacy_gcp` は設定リファレンスに記載がない
- `tui.notification_method` の documented な値は `auto` / `osc9` / `bel` の 3 つで、`osc777` は含まれない
- `features.multi_agent` は起動時に警告が出るようになったが、設定リファレンスでは非推奨の印が付いていない

---

設定例・手順の全文はこちらで公開しています: [Codex CLI v0.168 と v0.169 の変更点と codex exec の --trust が必要になる場面](https://aicoding-guide.com/posts/codex-update-0-169/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
