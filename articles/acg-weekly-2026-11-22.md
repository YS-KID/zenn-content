---
title: "今週の Claude Code・Codex・Gemini CLI 変更点まとめ(2026年11月22日週)"
emoji: "🛠️"
type: "tech"
topics: ["ai", "claudecode", "codex", "geminicli"]
published: false
---

今週いちばん影響が大きいのは、**Claude Code v2.1.328 で Amazon Bedrock・Google Cloud's Agent Platform・Microsoft Foundry・Claude apps gateway でも auto モードが使えるようになった**ことです。追加されただけでなく、**権限モードを指定していない対話セッションはそのモードで始まります**。サードパーティプロバイダー経由で使っている場合、設定を変えていなくても確認プロンプトの出方が変わります。

Codex は 3 本、Gemini CLI は 2 本出ました。Gemini CLI のほうは権限ポリシーの照合に関わる修正が複数まとまっています。

> **要点**
> 今週の要点
>
> - Claude Code v2.1.328 で auto モードがサードパーティプロバイダーに対応し、モード未指定の対話セッションの開始モードになった
> - Codex v0.171.0 で GPT-6.2 Sol が既定の選択になり、TUI workspace が既定で有効になった
> - Gemini CLI v0.69.0 と v0.70.0 で、シェルコマンドの許可判定とポリシーの照合が複数直った

## まとめ

- 今週は Claude Code 5 本、Codex 3 本、Gemini CLI 2 本の計 10 本
- 最優先は Claude Code v2.1.328 の auto モードのサードパーティプロバイダー対応。既定の開始モードが変わる
- Codex v0.171.0 で GPT-6.2 Sol が既定の選択になり、TUI workspace が既定で有効になった
- Codex v0.170.0 は、権限の更新と子スレッドがサンドボックスの制限を失う問題を修正している
- Gemini CLI は v0.69.0 と v0.70.0 で、権限ポリシーの照合とシェルコマンドの許可判定を複数直した

---

設定例・手順の全文はこちらで公開しています: [今週の Claude Code・Codex・Gemini CLI 変更点まとめ(2026年11月22日週)](https://aicoding-guide.com/posts/weekly-2026-11-22/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
