---
title: "Claude Code の Stop フックで作業完了をデスクトップ通知する設定"
emoji: "🤖"
type: "tech"
topics: ["claudecode", "hooks", "stop"]
published: false
---

長い作業を投げたあと、ターミナルを見張っているのは時間の無駄です。終わった瞬間に通知が来れば、その間は別の作業ができます。

Claude が応答を終えたタイミングで発火するのは **`Stop` フック**です。公式ドキュメントの入門で扱われている `Notification` フックは「入力待ち」を知らせるもので、目的が違います。この記事では両者を区別したうえで、3 つの OS それぞれの設定を示します。

> **要点**
> この記事で分かること
>
> - `Stop` と `Notification` の違いと、どちらを使うべきか
> - macOS・Linux・Windows それぞれの通知コマンドと設定例
> - 終了コードの落とし穴(通知スクリプトで Claude が止まらなくなる)

## まとめ

- 作業完了の通知は `Stop`、入力待ちの通知は `Notification` を使う
- `Stop` は matcher に対応していない。書いても黙って無視される
- macOS は `osascript`、Linux は `notify-send`、Windows は PowerShell の MessageBox
- `Stop` フックが終了コード 2 を返すと停止がブロックされる。通知だけなら `|| true` で 0 にする
- 意図的にブロックするなら `stop_hook_active` を見て 8 回連続の上限を避ける
- `last_assistant_message` を使うと、何が終わったのかを通知に含められる

---

設定例・手順の全文はこちらで公開しています: [Claude Code の Stop フックで作業完了をデスクトップ通知する設定](https://aicoding-guide.com/posts/claude-code-hooks-stop-notify/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
