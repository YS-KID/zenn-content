---
title: "Codex CLI v0.170 の変更点と permissions プロファイルが sandbox_mode に負ける条件"
emoji: "🧭"
type: "tech"
topics: ["codex", "codexcli", "permissions"]
published: true
---

Codex CLI の v0.170.0 は、**サンドボックスの制限が失われる問題の修正**が入ったリリースです。緩む方向の不具合なので、更新を後回しにする理由がありません。

同時にドキュメントも更新され、permissions プロファイルとファイルシステムのルールの説明が追加されました。読んでみると、**プロファイルを書いても無視される条件**が明記されています。ここを知らないと設定が効かない理由が分かりません。

> **要点**
> この記事で分かること
>
> - v0.170.0 で直った「サンドボックスの制限の喪失」が何だったのか
> - permissions プロファイルの書き方と、組み込みプロファイル 3 つの違い
> - `sandbox_mode` が残っていると `default_permissions` が無視される条件

## まとめ

- v0.170.0 は、権限の更新と子スレッドが既存のサンドボックス制限を失う問題を修正した。ドキュメントは本来「Subagents inherit your current sandbox policy」と定めている
- permissions プロファイルは `[permissions.<name>]` で宣言し、`default_permissions` で選ぶ。組み込みは `:read-only`、`:workspace`、`:danger-full-access` の 3 つ
- **`sandbox_mode` がどこかの設定ファイルに残っていると、`default_permissions` は無視される。** 併用はできず、古い設定が優先される
- filesystem のルールは空だと制限されたまま警告が出る。deny のグロブはサンドボックスのプロセス開始時に展開され、後から作られたファイルには効かない
- プロファイルは Beta で、仕様が変わる可能性がある

---

設定例・手順の全文はこちらで公開しています: [Codex CLI v0.170 の変更点と permissions プロファイルが sandbox_mode に負ける条件](https://aicoding-guide.com/posts/codex-update-0-170/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
