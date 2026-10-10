---
title: "Claude Code の hooks の入出力仕様、stdin の JSON の構造と終了コード 0・2・その他の意味"
emoji: "🤖"
type: "tech"
topics: ["claudecode", "hooks", "json", "jq", "pretooluse"]
published: false
---

hooks でスクリプトを実行する設定は書けたものの、そのスクリプトの中で「どのファイルが編集されたのか」をどう知るのか、そして lint が失敗したことをどう Claude に伝えるのかが分かりません。この 2 つは hooks の「入力」と「出力」の仕様で、どちらも押さえないと、lint が失敗しても Claude が気付かない、あるいは警告のつもりが処理を止めてしまう、という食い違いが起きます。

結論として、入力は**標準入力に流れてくる JSON**、出力は**終了コード**です。コマンド型のフックは stdin から JSON を受け取り、HTTP 型のフックは同じ JSON を `Content-Type: application/json` の POST ボディとして受け取ります。終了コードは 0 が成功、2 がブロック(標準エラー出力が Claude に渡る)、それ以外が警告(ユーザーに表示、処理は続行)です。

> **要点**
> この記事で分かること
>
> - 全イベント共通で入る JSON の項目と、PreToolUse・Stop・SessionStart などイベント別に追加される項目
> - `jq` で値を取り出す実例と、JSON にない情報の取得方法
> - 終了コード 0 / 2 / その他の挙動の違いと、イベントごとの「ブロック」の意味
> - 標準出力の JSON による細かい制御

## まとめ

- コマンド型のフックは stdin から JSON を受け取る。共通項目は `session_id`、`cwd`、`permission_mode`、`hook_event_name`、`effort` など。ツールのイベントでは `tool_name`、`tool_input`、`tool_use_id` が入る
- 項目名はイベントごとに違う(`SessionStart` は `how`、`SessionEnd` は `why`、`PreCompact` は `what`)
- スクリプトでは `INPUT=$(cat)` で保持し、`jq -r '... // empty'` で取り出す。プロジェクトルートは `$CLAUDE_PROJECT_DIR`
- 終了コード 0 は成功、2 はブロック(標準エラー出力が Claude に渡る)、その他は警告(ユーザーに表示)。PostToolUse の 2 は取り消しではなく修正指示
- `PermissionRequest` は 2 を無視する。JSON 制御のフィールドはイベントごとに違い、標準出力には JSON 以外を出さない

---

設定例・手順の全文はこちらで公開しています: [Claude Code の hooks の入出力仕様、stdin の JSON の構造と終了コード 0・2・その他の意味](https://aicoding-guide.com/posts/claude-code-hooks-stdin-json/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
