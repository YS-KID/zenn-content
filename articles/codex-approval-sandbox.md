---
title: "Codex CLI の approval mode と sandbox 設定の違い:安全に自動実行させる組み合わせ"
emoji: "🧭"
type: "tech"
topics: ["codex", "codexcli"]
published: true
---

Codex CLI の安全性は、**承認ポリシー(approval)** と **サンドボックス(sandbox)** の 2 つの独立した設定で決まります。この 2 つを混同すると、「確認なしにしたのにコマンドが失敗する」「確認しているのにファイルが書き換わっていた」といった混乱が起きます。

この記事では、それぞれの選択肢の意味、組み合わせたときの挙動、用途別の推奨設定を整理します。

> **要点**
> この記事で分かること
>
> - 承認ポリシーとサンドボックスの役割の違い
> - 各選択肢の意味と、`--full-auto` の中身
> - 用途別(調査・日常開発・CI)の推奨設定と config.toml への書き方

## まとめ

- approval は「確認するか」、sandbox は「OS レベルで何ができるか」。独立した 2 つの設定
- 日常開発は `on-request` + `workspace-write`、調査は `read-only`、CI は `never`
- `--full-auto` は `workspace-write` で自律的に進める省略形。ワークスペース外やネットワークは制限される
- `danger-full-access` と `never` の組み合わせは隔離環境専用

---

設定例・手順の全文はこちらで公開しています: [Codex CLI の approval mode と sandbox 設定の違い:安全に自動実行させる組み合わせ](https://aicoding-guide.com/posts/codex-approval-sandbox/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
