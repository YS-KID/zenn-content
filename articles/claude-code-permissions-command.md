---
title: "Claude Code の /permissions コマンドでできること(ルール確認と追加)"
emoji: "🤖"
type: "tech"
topics: ["claudecode", "permissions"]
published: true
---

権限まわりのトラブルは、たいてい「今どのルールが効いているのか分からない」ことが原因です。`settings.json` はユーザー・プロジェクト・ローカル・管理者と複数の場所にあり、手で追いかけると見落とします。

`/permissions` は、その全部をまとめて表示するコマンドです。ルールの一覧と、それぞれがどの `settings.json` 由来かが表示され、その場で追加も削除もできます。

> **要点**
> この記事で分かること
>
> - `/permissions` で何が見えて、何を編集できるか
> - 追加したルールがどの設定ファイルに保存されるか
> - Auto mode タブと Recently denied タブの役割

## まとめ

- `/permissions` は全ルールと、その出どころの設定ファイルを一覧表示する
- 作業中でも開け、変更は同じターンの次のツール呼び出しから効く
- `/path` の起点は保存先の設定ファイルで変わるため、保存先を意識して書く
- 「Yes, and don't ask again」の恒久承認はリポジトリルートの `.claude/settings.local.json` に入る
- auto モードが使えるセッションでは Auto mode タブと Recently denied タブが増える

---

設定例・手順の全文はこちらで公開しています: [Claude Code の /permissions コマンドでできること(ルール確認と追加)](https://aicoding-guide.com/posts/claude-code-permissions-command/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
