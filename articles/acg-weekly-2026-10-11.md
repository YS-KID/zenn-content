---
title: "今週の Claude Code・Codex・Gemini CLI 変更点まとめ(2026年10月11日週)"
emoji: "🛠️"
type: "tech"
topics: ["ai", "claudecode", "codex", "geminicli"]
published: true
---

今週いちばん影響が大きいのは **Claude Haiku 5.5** の追加です。Anthropic API の既定 Haiku モデルになり、コンテキストは 100 万トークン、短いプロンプトの料金は Haiku 4.5 の 10 分の 1 になりました。Codex 側では **既定モデルが GPT-6.1 Sol** に変わっています。

あわせて Claude Code には、権限ルールが取りこぼされていた不具合の修正が複数入りました。サンドボックスやフックに権限の判断を任せている場合は、早めに当てたほうがよい内容です。

> **要点**
> 今週の要点
>
> - Claude Haiku 5.5 が API の既定 Haiku になった(1M コンテキスト、$0.10 / $0.50)
> - Claude Code で Bash の deny・ask ルールの取りこぼしと、UNC パス読み取りの権限バイパスが修正された
> - Codex の既定モデルが GPT-6.1 Sol になり、Daybreak は明示的な opt-in になった

## まとめ

- Claude Haiku 5.5 が API の既定 Haiku になった。1M コンテキストで、10 万トークン以下なら $0.10 / $0.50
- Claude Code 2.1.289〜2.1.292 に権限ルールの取りこぼしの修正が集中。UNC パス読み取りの件は Security 扱い
- `onFailure: "block"` で、フックが壊れたときに処理を止められるようになった
- Codex の既定モデルは同梱・Bedrock のカタログで GPT-6.1 Sol に。Daybreak は `cli_daybreak` での opt-in が必要
- Gemini CLI v0.63.0 は修正のみ

---

設定例・手順の全文はこちらで公開しています: [今週の Claude Code・Codex・Gemini CLI 変更点まとめ(2026年10月11日週)](https://aicoding-guide.com/posts/weekly-2026-10-11/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
