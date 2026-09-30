---
title: "今週の Claude Code・Codex・Gemini CLI 変更点まとめ(2026年9月27日週)"
emoji: "🛠️"
type: "tech"
topics: ["ai", "claudecode", "codex", "geminicli"]
published: false
---

今週の最大の変更は、**Claude Opus 5.5(`claude-opus-5-5`)が Claude Code の既定の Opus モデルになった**ことです(v2.1.280)。公式の料金表では入力 $4/MTok・出力 $20/MTok で、Claude Opus 5 の $5/$25 より安くなっています。

権限まわりでは、シンボリックリンク経由の書き込みが誤って承認される問題が同じ 2.1.280 で修正されました。設定面では `"attribution": false` という短い書き方が増え、auto モードの分類器がサーバー側に移りました。

対象は Claude Code 2.1.278・2.1.280〜2.1.283、Codex CLI 0.156.1 / 0.157.0、Gemini CLI 0.61.0 です。

> **要点**
> この記事で分かること
>
> - Claude Opus 5.5 のモデル ID と、公式料金表で確認できる価格
> - シンボリックリンク経由の書き込み判定の修正と、auto モードの変更点
> - Codex の GPT-6 Sol / Luna 追加と、Gemini CLI 0.61.0 のセキュリティ修正

## まとめ

- Claude Opus 5.5(`claude-opus-5-5`)が Claude Code の既定の Opus モデルになり、公式料金表では入力 $4/MTok・出力 $20/MTok でした
- 2.1.280 でシンボリックリンク経由の書き込みが実際の着地先で判定されるようになり、auto モードの再試行ループも 2 件修正されました
- 2.1.281 の `"attribution": false` は便利ですが、古い CLI が設定ファイルごと読み飛ばす点に注意が必要です
- Codex 0.157.0 は GPT-6 Sol と Luna を追加し、全画面トランスクリプトが既定になりました
- Gemini CLI 0.61.0 はプロンプトインジェクション対策とサンドボックス強化が中心で、新機能はありません

---

設定例・手順の全文はこちらで公開しています: [今週の Claude Code・Codex・Gemini CLI 変更点まとめ(2026年9月27日週)](https://aicoding-guide.com/posts/weekly-2026-09-27/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
