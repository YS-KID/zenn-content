---
title: "Claude Code でどの CLAUDE.md がいつ読まれたかを記録する InstructionsLoaded フックの使い方"
emoji: "🤖"
type: "tech"
topics: ["claudecode", "hooks", "instructionsloaded", "claudemd"]
published: false
---

「このルール、本当に読み込まれているのか」「サブディレクトリの CLAUDE.md はいつ読まれたのか」を調べるとき、`/context` の一覧だけでは時系列が分かりません。Claude Code には、指示ファイルが読み込まれるたびに発火する **InstructionsLoaded** フックがあり、ファイル名・理由・トリガーになったファイルを外部に記録できます。

結論として、`hooks.InstructionsLoaded` に `load_reason` を matcher にしたコマンドを登録し、標準入力の JSON を jq で取り出してログに追記すれば、どの指示がいつ効き始めたかを追えます。

> **要点**
> この記事で分かること
>
> - InstructionsLoaded が発火するタイミングと、matcher に使える `load_reason` の値
> - 入力 JSON のフィールド(`file_path`、`memory_type`、`globs`、`trigger_file_path` など)
> - ログを残すフックの設定例と、このフックでは「できないこと」

## まとめ

- InstructionsLoaded は CLAUDE.md と `.claude/rules/*.md` が読み込まれるたびに発火する非同期フック
- matcher は `load_reason`(`session_start` / `nested_traversal` / `path_glob_match` / `include` / `compact`)に対して評価される
- 入力には `file_path`、`memory_type`、`globs`、`trigger_file_path`、`parent_file_path` が含まれる
- ブロックも書き換えもできない。用途はログ・監査・可観測性
- 読み込みを止めたいなら `claudeMdExcludes` を使う

---

設定例・手順の全文はこちらで公開しています: [Claude Code でどの CLAUDE.md がいつ読まれたかを記録する InstructionsLoaded フックの使い方](https://aicoding-guide.com/posts/claude-code-instructions-loaded-hook/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
