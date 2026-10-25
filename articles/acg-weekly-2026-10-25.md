---
title: "今週の Claude Code・Codex・Gemini CLI 変更点まとめ(2026年10月25日週)"
emoji: "🛠️"
type: "tech"
topics: ["ai", "claudecode", "codex", "geminicli"]
published: true
---

今週は **セキュリティ修正の週**でした。Claude Code 2.1.309 に、サンドボックスと権限チェックをすり抜けられる経路の修正が 10 件以上まとまって入っています。Codex 0.164.0 もサンドボックスの判定を固め、資格情報のマスクを追加しました。

Codex 側には新機能もあります。`/presets` でプロンプトとスラッシュコマンドを 10 個のスロットに保存できるようになり、`/model` と `/permissions` が引数で直接指定できるようになりました。

> **要点**
> 今週の要点
>
> - Claude Code 2.1.309 にサンドボックスと権限チェックの抜け穴の修正が集中した
> - Codex 0.164.0 で `/presets` と、リモート Bash の資格情報マスクが入った
> - Claude Code に `claude_code.safety_event` の OpenTelemetry イベントが追加された

## まとめ

- Claude Code 2.1.309 に、サンドボックスと権限チェックをすり抜けられる経路の修正が 10 件以上入った
- サンドボックス対象のコマンドの前に、シェルの起動ファイルがサンドボックスの外で実行されていた
- `claude_code.safety_event` で、止められた・確認が出たツール呼び出しを計測できるようになった
- Codex 0.164.0 は `/presets`、`/model` と `/permissions` の引数、資格情報のマスクを追加した
- Gemini CLI v0.65.0 は未信頼フォルダの設定の強制と `otlpHeaders` の追加

---

設定例・手順の全文はこちらで公開しています: [今週の Claude Code・Codex・Gemini CLI 変更点まとめ(2026年10月25日週)](https://aicoding-guide.com/posts/weekly-2026-10-25/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
