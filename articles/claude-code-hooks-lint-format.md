---
title: "Claude Code の編集後に lint と format を走らせる:PostToolUse と Edit|Write|MultiEd"
emoji: "🤖"
type: "tech"
topics: ["claudecode", "hooks", "lint", "prettier"]
published: false
---

「フォーマットを揃えてからコミットして」と CLAUDE.md に書いても、Claude が実行を忘れることがあります。指示は確率的に守られるものだからです。この問題を確実に解決するのが **hooks** です。hooks は Claude の判断を介さず、Claude Code 本体が決められたタイミングでシェルコマンドを実行する仕組みです。

この記事では、Claude がファイルを編集するたびに Prettier や ESLint、Python なら ruff を自動実行し、失敗したら Claude 自身に修正させる設定を作ります。

> **要点**
> この記事で分かること
>
> - hooks のイベント種類と設定ファイルの書き方
> - 編集されたファイルだけを対象に lint / format を走らせる方法
> - lint 失敗を Claude にフィードバックして自動修正させる方法

## まとめ

- hooks は Claude の判断を介さず確実に実行されるため、lint / format の自動化に向いている
- `PostToolUse` + `matcher: "Edit|Write|MultiEdit"` で編集後に走らせる
- stdin の JSON から `tool_input.file_path` を取り出し、編集されたファイルだけを対象にする
- 終了コード 2 と標準エラー出力で、Claude に修正を促せる

---

設定例・手順の全文はこちらで公開しています: [Claude Code の編集後に lint と format を走らせる:PostToolUse と Edit|Write|MultiEdit](https://aicoding-guide.com/posts/claude-code-hooks-lint-format/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
