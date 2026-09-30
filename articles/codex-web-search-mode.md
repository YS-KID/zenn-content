---
title: "Codex の Web 検索を制御する web_search 設定:disabled / cached / indexed / live の"
emoji: "🧭"
type: "tech"
topics: ["codex", "configtoml", "websearch", "web"]
published: false
---

依存ライブラリの最新のリリースノートを踏まえて作業してほしいときは Web 検索が要りますが、常に外部の Web を読ませるとプロンプトインジェクションの入り口になります。Codex CLI の Web 検索は `web_search` 設定で 4 段階に制御できます。

結論として、`config.toml` の `web_search` に `disabled` / `cached` / `indexed` / `live` のいずれかを書きます。ローカルの既定は `cached` で、1 回だけライブ検索を使いたいときは `--search` フラグで起動します。

> **要点**
> この記事で分かること
>
> - 4 つの値の意味と、それぞれの既定になる条件
> - `--search` フラグでの一時的な有効化
> - `indexed` がプロンプトインジェクション対策になる理由と、ドメイン制限

## まとめ

- `web_search` は `disabled` / `cached` / `indexed` / `live` の 4 段階。ローカルの既定は `cached`、フルアクセス時はライブ
- そのタスクだけ使うなら `codex --search "..."`
- `indexed` は検索インデックスをゲートにして、任意ページの直接読み込みを防ぐ
- `tools.web_search.allowed_domains` でドメインを絞れるが、コマンドや MCP の通信には効かない
- `features.web_search` は非推奨。Web の結果は常に信頼できない入力として扱う

---

設定例・手順の全文はこちらで公開しています: [Codex の Web 検索を制御する web_search 設定:disabled / cached / indexed / live の違い](https://aicoding-guide.com/posts/codex-web-search-mode/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
