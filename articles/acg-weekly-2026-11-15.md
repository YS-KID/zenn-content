---
title: "今週の Claude Code・Codex・Gemini CLI 変更点まとめ(2026年11月15日週)"
emoji: "🛠️"
type: "tech"
topics: ["ai", "claudecode", "codex", "geminicli"]
published: false
---

今週いちばん影響が大きいのは、**Claude Code v2.1.321 の権限とサンドボックスの修正 4 件**です。いずれも「確認が出るはずの操作が出なかった」種類の抜けで、設定を変えずに挙動が変わります。更新を後回しにする理由がない回です。

新機能としては v2.1.323 の **Code Mode**(Claude が JavaScript を書いてツールを呼ぶ実験的な方式)が入りました。Codex は 0.167.1 から 0.169.0 まで 4 本出ています。

> **要点**
> 今週の要点
>
> - Claude Code v2.1.321 が権限・サンドボックスの抜けを 4 件、v2.1.325 が zstd 復号のセキュリティ問題を修正
> - v2.1.323 で Code Mode が実験的オプトインとして追加。`plugin.json` の `engines` によるバージョン範囲の判定も入った
> - Codex v0.169.0 で `codex exec` の信頼判定が変わり、`--sandbox workspace-write` だけでは project 設定と MCP が有効にならない

## まとめ

- 今週は Claude Code 4 本、Codex 4 本、Gemini CLI 1 本の計 9 本
- 最優先は Claude Code v2.1.321 の権限・サンドボックス修正 4 件と、v2.1.325 の zstd 復号のセキュリティ修正
- v2.1.323 で Code Mode が実験的オプトインとして追加。プラグインは `engines["claude-code"]` でバージョン範囲が判定されるようになった
- Codex v0.169.0 で `codex exec` の信頼判定が変わり、`--sandbox workspace-write` だけでは project 設定と MCP が有効にならない
- Gemini CLI v0.68.0 はサンドボックスとパス解決の修正が中心で、新機能は拡張の検証コマンド 1 件

---

設定例・手順の全文はこちらで公開しています: [今週の Claude Code・Codex・Gemini CLI 変更点まとめ(2026年11月15日週)](https://aicoding-guide.com/posts/weekly-2026-11-15/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
