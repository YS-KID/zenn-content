---
title: "今週の Claude Code・Codex・Gemini CLI 変更点まとめ(2026年11月1日週)"
emoji: "🛠️"
type: "tech"
topics: ["ai", "claudecode", "codex", "geminicli"]
published: false
---

今週は **期限のある変更**があります。Opus 4.8 の fast モードが 2026 年 10 月 30 日付で非推奨になり、**2026 年 11 月 30 日に削除**されます。CHANGELOG は、削除後は fast モードのリクエストがエラーになり、通常の Opus 4.8 にフォールバックもしないと書いています。

機能面では、アイドル時の自動コンパクトが VS Code とデスクトップアプリにも広がりました。2 週間前にターミナル限定で入った機能です。

> **要点**
> 今週の要点
>
> - Opus 4.8 の fast モードが 11 月 30 日に削除される。速度を保つなら Opus 5.5 へ
> - アイドル時の自動コンパクトが VS Code とデスクトップの Code タブに追加された
> - `permissions.blockWritesOutsideWorkingDirectories` が追加された

## まとめ

- Opus 4.8 の fast モードは 2026 年 11 月 30 日に削除され、エラーになる。フォールバックはない
- アイドル時の自動コンパクトが VS Code とデスクトップアプリの Code タブに追加された
- `permissions.blockWritesOutsideWorkingDirectories` で書き込みを作業ディレクトリ内に閉じられる
- `claude_code.safety_event` は追加の 1 週間後に送信が止まった
- Codex 0.166.0 は `codex queue --resume` と `codex doctor --network-only` を追加した

---

設定例・手順の全文はこちらで公開しています: [今週の Claude Code・Codex・Gemini CLI 変更点まとめ(2026年11月1日週)](https://aicoding-guide.com/posts/weekly-2026-11-01/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
