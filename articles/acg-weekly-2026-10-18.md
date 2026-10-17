---
title: "今週の Claude Code・Codex・Gemini CLI 変更点まとめ(2026年10月18日週)"
emoji: "🛠️"
type: "tech"
topics: ["ai", "claudecode", "codex", "geminicli"]
published: false
---

今週いちばん影響が大きいのは、Claude Code の **アイドル時の自動コンパクト**です。長い会話を放置すると、こちらが何もしなくても要約が走るようになりました。

Codex 側では **Daybreak が既定で有効に戻りました**。5 日前の v0.161.0 で明示的な opt-in が必要になったばかりの設定で、短い間に 2 回変わっています。

> **要点**
> 今週の要点
>
> - Claude Code がアイドル時に自動コンパクトするようになった(`idleCompaction` で停止)
> - Codex 0.163.0 で Daybreak が対象アカウントの既定に戻った
> - Claude Code に `CLAUDE_CODE_DISABLE_FILE_MENTIONS` と `CLAUDE_CODE_AUTO_MODE_MODEL` が追加された

## まとめ

- Claude Code がアイドル時に自動コンパクトするようになった。20 万トークン超を 54 分放置すると走る
- 止めるのは `"idleCompaction": false`、しきい値は `CLAUDE_CODE_IDLE_COMPACT_MIN_TOKENS`、切り替えは `/config`
- `CLAUDE_CODE_DISABLE_FILE_MENTIONS` で `@` 参照を中身ではなくパスにできる
- Codex 0.163.0 で Daybreak が対象アカウントの既定に戻った。5 日で 2 回変わっている
- Gemini CLI v0.64.0 は修正のみ

---

設定例・手順の全文はこちらで公開しています: [今週の Claude Code・Codex・Gemini CLI 変更点まとめ(2026年10月18日週)](https://aicoding-guide.com/posts/weekly-2026-10-18/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
