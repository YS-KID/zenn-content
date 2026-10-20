---
title: "今週の Claude Code・Codex・Gemini CLI 変更点まとめ(2026年9月13日週)"
emoji: "🛠️"
type: "tech"
topics: ["ai", "claudecode", "codex", "geminicli"]
published: true
---

今週は 3 ツールとも、機能追加より**権限とセキュリティの穴をふさぐ修正**が目立ちました。とくに影響が大きいのは Claude Code 2.1.268 で、`deny` ルールが効かないケースが 2 種類修正されています。`deny` を前提にコードベースを守っている場合は、更新を優先してください。

対象は Claude Code 2.1.268 / 2.1.269、Codex CLI 0.154.0、Gemini CLI 0.59.0 です。

> **要点**
> この記事で分かること
>
> - Claude Code の `deny` ルールがすり抜けていた 2 つのケースと、その修正
> - Codex CLI 0.154.0 の破壊的変更(`codex mcp-server` の削除)と新機能
> - Gemini CLI 0.59.0 に入った MCP 関連のセキュリティ修正

## まとめ

- 今週は 3 ツールとも権限・セキュリティ修正が中心で、機能追加は Codex が最多
- Claude Code 2.1.268 は `deny` ルールのすり抜けを 2 件修正しており、更新の優先度が高い
- `/mcp` や `claude mcp list` が `${VAR}` から解決した秘密情報を表示する問題も同リリースで修正された
- Codex 0.154.0 は `codex mcp-server` を削除した破壊的変更を含む。worktree と GPT-6-Astra が追加
- Gemini CLI 0.59.0 は MCP の SSRF 修正と fail-closed なワークスペース信頼の 2 件

---

設定例・手順の全文はこちらで公開しています: [今週の Claude Code・Codex・Gemini CLI 変更点まとめ(2026年9月13日週)](https://aicoding-guide.com/posts/weekly-2026-09-13/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
