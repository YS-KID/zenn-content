---
title: "Claude Code を非対話モード(claude -p)で使う:CI やスクリプトから呼び出す方法"
emoji: "🤖"
type: "tech"
topics: ["claudecode", "ci"]
published: false
---

Claude Code は対話的に使うのが基本ですが、`-p`(print)オプションを付けると、1 つの指示を渡して結果を標準出力に返す**非対話モード**になります。シェルスクリプト、cron、CI パイプラインから呼び出せるため、「PR の差分を要約する」「テスト失敗の原因を分析する」「ドキュメントを更新する」といった処理を自動化できます。

この記事では、基本的な呼び出し方から、出力の JSON 化、ツール許可、CI で暴走させないための制御までを扱います。

> **要点**
> この記事で分かること
>
> - `claude -p` の基本と、標準入力・ファイルの渡し方
> - `--output-format json` による結果のプログラム処理
> - CI で安全に動かすための権限・ターン数・コストの制御

## まとめ

- `claude -p "指示"` で非対話実行。標準入力でデータを渡せる
- `--output-format json` で本文・コスト・セッション ID を取得し、`jq` で処理する
- 編集や実行は `--allowedTools` で明示的に許可し、`--max-turns` で上限を設ける
- `--dangerously-skip-permissions` は使い捨ての隔離環境に限定する

---

設定例・手順の全文はこちらで公開しています: [Claude Code を非対話モード(claude -p)で使う:CI やスクリプトから呼び出す方法](https://aicoding-guide.com/posts/claude-code-headless-ci/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
