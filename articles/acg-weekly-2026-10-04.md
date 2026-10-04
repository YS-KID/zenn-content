---
title: "今週の Claude Code・Codex・Gemini CLI 変更点まとめ(2026年10月4日週)"
emoji: "🛠️"
type: "tech"
topics: ["ai", "claudecode", "codex", "geminicli"]
published: true
---

今週の最大の変更は、**Claude Sonnet 5.5(`claude-sonnet-5-5`)が Anthropic API の既定の Sonnet モデルになった**ことです(v2.1.284)。公式料金表の価格は Sonnet 5 と同額なので、値上げを気にせず切り替わります。

機能面では、プラグインの仕組みを拡張する **Claude Mods** が 2.1.287 で追加されました。設定面では `CLAUDE_CODE_DISABLE_WEB_FETCH` と `allowedProviders` が増えています。

対象は Claude Code 2.1.284〜2.1.288、Codex CLI 0.160.0、Gemini CLI 0.62.0 です。

> **要点**
> この記事で分かること
>
> - Claude Sonnet 5.5 のモデル ID と、公式料金表で確認できる価格
> - Claude Mods と、新しく増えた 3 つの設定
> - セッション再開と自動圧縮まわりの修正

## まとめ

- Claude Sonnet 5.5(`claude-sonnet-5-5`)が Anthropic API の既定の Sonnet モデルになり、価格は Sonnet 5 と同額でした
- 2.1.287 の Claude Mods でプラグインがより深い挙動を変更できるようになり、組み込みの「You should know」が追加されました
- 2.1.285 で `CLAUDE_CODE_DISABLE_WEB_FETCH` と `allowedProviders` が増え、止められる範囲が広がりました
- 2.1.288 は自動圧縮と `--resume` の取りこぼしを複数修正しています
- Codex 0.160.0 は Windows まわりの修正が中心、Gemini CLI 0.62.0 は新モデル 2 つの追加が中心です

---

設定例・手順の全文はこちらで公開しています: [今週の Claude Code・Codex・Gemini CLI 変更点まとめ(2026年10月4日週)](https://aicoding-guide.com/posts/weekly-2026-10-04/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
