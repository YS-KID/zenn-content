---
title: "Codex の --full-auto は何をするのか:承認とサンドボックスの中身"
emoji: "🧭"
type: "tech"
topics: ["codex", "fullauto"]
published: true
---

`codex --full-auto` は「全部自動でやる」という名前に見えますが、実際には**ワークスペースの中だけ自由にしてよい**という設定です。ワークスペースの外に書き込んだり、ネットワークに出たりすることは、サンドボックスによって引き続き制限されます。

もう 1 点先に押さえておきます。公式ドキュメントは現在 `--full-auto` を**非推奨**としており、代わりに `codex exec --sandbox workspace-write` を案内しています。フラグ自体は動作するため、何に相当するかを知っておくと置き換えられます。

> **要点**
> この記事で分かること
>
> - `--full-auto` が設定する承認ポリシーとサンドボックスの組み合わせ
> - 自動で通るもの、制限されるもの
> - config.toml で同じ設定を固定する方法と、使うべき場面

## まとめ

- `--full-auto` は `approval_policy = "on-request"` と `sandbox_mode = "workspace-write"` の省略形。公式は非推奨とし `codex exec --sandbox workspace-write` を案内している
- ネットワークが必要な操作は失敗して確認が入る。`network_access = true` で許可できる
- サンドボックスは読み取りを制限しないため、秘密情報はワークスペース外に置く
- 調査は `read-only`、テストが整ったリポジトリのリファクタリングは `--full-auto` が向いている

---

設定例・手順の全文はこちらで公開しています: [Codex の --full-auto は何をするのか:承認とサンドボックスの中身](https://aicoding-guide.com/posts/codex-full-auto/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
