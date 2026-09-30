---
title: "Claude Code のサブエージェント(.claude/agents)の作り方と使いどころ"
emoji: "🤖"
type: "tech"
topics: ["claudecode", "agents"]
published: false
---

コードベース全体を調べさせると、Claude が読んだファイルの内容がすべてコンテキストに残り、その後の作業精度が落ちます。レビューを頼むと、レビュー観点の長い指示が本来のタスクと混ざります。

こうした問題を解決するのが **サブエージェント**です。サブエージェントは独立したコンテキストと専用の指示を持つ Claude で、メインの Claude が必要に応じて呼び出します。この記事では、定義ファイルの書き方と、効果が出やすい使い方を解説します。

> **要点**
> この記事で分かること
>
> - `.claude/agents/` に置く定義ファイルの書き方
> - tools・model の指定と、description による自動呼び出しの制御
> - 調査用・レビュー用・テスト用の実例

## まとめ

- `.claude/agents/<名前>.md` に name / description / tools / model と本文を書く
- description に「いつ使うか」を具体的に書くと自動呼び出しが安定する
- 調査は読み取り専用 + 軽量モデル、レビューは高性能モデル、のように役割ごとに設定する
- サブエージェントはメインの会話を知らないため、委任時に必要な情報をすべて渡す

---

設定例・手順の全文はこちらで公開しています: [Claude Code のサブエージェント(.claude/agents)の作り方と使いどころ](https://aicoding-guide.com/posts/claude-code-subagents/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
