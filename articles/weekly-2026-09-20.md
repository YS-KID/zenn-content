---
title: "今週の Claude Code・Codex・Gemini CLI 変更点まとめ(2026年9月20日週)"
emoji: "🛠️"
type: "tech"
topics: ["ai", "claudecode", "codex", "geminicli"]
published: false
---

今週の最大の変更は Claude Code が **`AGENTS.md` を直接読むようになった**ことです(v2.1.277)。これまでは `CLAUDE.md` からインポートする必要がありましたが、`CLAUDE.md` のないリポジトリならそのまま読まれます。

もう 1 点、先週このまとめで「権限のすり抜けが直った」と紹介した 2.1.268 の変更が **2.1.273 で差し戻されました**。該当する運用をしている場合は挙動が戻っている点に注意してください。

対象は Claude Code 2.1.270〜2.1.277、Codex CLI 0.155.0 / 0.155.1、Gemini CLI 0.60.0 です。

> **要点**
> この記事で分かること
>
> - Claude Code の `AGENTS.md` 対応と、どちらのファイルが読まれるかの判定
> - 先週紹介した deny ルールの修正が差し戻された件
> - Codex の音声会話と Touch ID、Gemini CLI のセキュリティ修正

## まとめ

- Claude Code v2.1.277 が `AGENTS.md` の直接読み込みに対応。`CLAUDE.md` がないリポジトリで有効になる
- 既定は `claude-md-or-agents-md`。両方読ませるには `/config` の Project instructions を変える
- 2.1.268 の deny ルール変更は 2.1.273 で差し戻された。先週の本まとめの記述を訂正する
- 2.1.275 はゲートウェイ経由で全リクエストが 400 になるリグレッションがあり、2.1.276 で修正
- Codex 0.155.0 は実験的な `/voice` と MCP の Touch ID 確認を追加。0.155.1 は推論サマリーの既定を元に戻す修正
- Gemini CLI 0.60.0 はセキュリティ修正が中心で、MCP OAuth の RFC 9207 強制や拡張機能の境界検証が入った

---

設定例・手順の全文はこちらで公開しています: [今週の Claude Code・Codex・Gemini CLI 変更点まとめ(2026年9月20日週)](https://aicoding-guide.com/posts/weekly-2026-09-20/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
