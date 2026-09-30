---
title: "Codex の完了通知は notify = ['python3', '通知.py']:デスクトップ通知と Slack への送り方"
emoji: "🧭"
type: "tech"
topics: ["codex", "configtoml", "notify", "tui"]
published: false
---

Codex に長めのタスクを任せて別の作業をしていると、終わったことに気づかず放置してしまいます。Codex CLI には、ターン完了時に **外部プログラムを起動する** `notify` と、ターミナル自体の通知を制御する `tui.notifications` の 2 つの仕組みがあります。

結論として、`notify = ["python3", "/path/to/notify.py"]` のように argv 配列を書くと、ターン完了ごとに JSON を 1 引数として受け取るプログラムが起動します。デスクトップ通知でも Slack の Webhook でも、そのプログラムで好きな処理ができます。

> **要点**
> この記事で分かること
>
> - `notify` の書き方と、プログラムに渡される JSON のフィールド
> - `tui.notifications` で通知の種類・条件・方式を絞る方法
> - macOS / Linux でデスクトップ通知を出すスクリプト例

## まとめ

- `notify` は argv 配列。ターン完了(`agent-turn-complete`)のたびに JSON 1 引数でプログラムを起動する
- JSON には `type`、`thread-id`、`turn-id`、`cwd`、`input-messages`、`last-assistant-message` が入る
- macOS は `terminal-notifier`、Linux は `notify-send` を直接指定するだけでも動く
- 外部サービスに送るときは本文を切り詰め、Webhook URL は環境変数に置く
- ターミナル通知は `[tui]` の `notifications` / `notification_condition` / `notification_method` で別に制御する

---

設定例・手順の全文はこちらで公開しています: [Codex の完了通知は notify = ["python3", "通知.py"]:デスクトップ通知と Slack への送り方](https://aicoding-guide.com/posts/codex-notify-turn-complete/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
