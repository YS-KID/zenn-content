---
title: "Claude Code の hooks が受け取る stdin JSON の構造:共通項目とイベント別の項目"
emoji: "🤖"
type: "tech"
topics: ["claudecode", "hooks", "json", "jq"]
published: true
---

hooks でスクリプトを実行する設定は書けたものの、そのスクリプトの中で「どのファイルが編集されたのか」「どのコマンドが実行されようとしているのか」をどう知るのかが分かりません。

答えは **標準入力に流れてくる JSON** です。コマンド型のフックは stdin から JSON を受け取り、HTTP 型のフックは同じ JSON を `Content-Type: application/json` の POST ボディとして受け取ります。この記事では、その JSON の構造を共通項目とイベント別項目に分けて整理します。

> **要点**
> この記事で分かること
>
> - 全イベント共通で入る項目と、それぞれの意味
> - PreToolUse・Stop・SessionStart などイベント別に追加される項目
> - `jq` で値を取り出す実例と、JSON にない情報の取得方法

## まとめ

- コマンド型のフックは stdin から JSON を受け取る。HTTP 型は同じ JSON を POST ボディで受け取る
- 共通項目は `session_id`、`transcript_path`、`cwd`、`permission_mode`、`hook_event_name`、`effort` など
- ツールのイベントでは `tool_name`、`tool_input`、`tool_use_id` が入り、`PostToolUse` では `tool_output` が加わる
- 項目名はイベントごとに違う(`SessionStart` は `how`、`SessionEnd` は `why`、`PreCompact` は `what`)
- スクリプトでは `INPUT=$(cat)` で保持し、`jq -r '... // empty'` で取り出す
- JSON にないプロジェクトルートは `$CLAUDE_PROJECT_DIR` から取得する

---

設定例・手順の全文はこちらで公開しています: [Claude Code の hooks が受け取る stdin JSON の構造:共通項目とイベント別の項目](https://aicoding-guide.com/posts/claude-code-hooks-stdin-json/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
