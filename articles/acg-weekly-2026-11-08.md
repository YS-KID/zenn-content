---
title: "今週の Claude Code・Codex・Gemini CLI 変更点まとめ(2026年11月8日週)"
emoji: "🛠️"
type: "tech"
topics: ["ai", "claudecode", "codex", "geminicli"]
published: false
---

今週いちばん影響が大きいのは、**auto モードが組み込みの分類器にフォールバックしなくなった**ことです。テレメトリや機能フラグを切っている環境、LLM ゲートウェイ越しの環境では、サーバー側で確認できない呼び出しが**確認か拒否**になります。

無人実行では `permissions.denyInsteadOfPrompting` が使えるようになりました。確認待ちで止まる代わりに拒否してターンを続けます。

> **要点**
> 今週の要点
>
> - auto モードが、サーバー側で確認できない呼び出しをフォールバックせず確認か拒否にするようになった
> - `permissions.denyInsteadOfPrompting` で、確認待ちを拒否に置き換えられる
> - Web とシェルのツール呼び出しがアカウントのメールアドレスを送る前に確認が入るようになった

## まとめ

- auto モードが、サーバー側で確認できない呼び出しをフォールバックせず確認か拒否にするようになった
- 戻すには `CLAUDE_CODE_AUTO_MODE_SERVER=0`。Bedrock・Vertex・Foundry は変更なし
- `permissions.denyInsteadOfPrompting` で、確認待ちを拒否に置き換えられる
- Web とシェルのツール呼び出しがアカウントのメールアドレスを送る前に確認が入る
- Codex 0.167.0 は `gcp_setup_wizard` とシステムプロキシの利用を追加した

---

設定例・手順の全文はこちらで公開しています: [今週の Claude Code・Codex・Gemini CLI 変更点まとめ(2026年11月8日週)](https://aicoding-guide.com/posts/weekly-2026-11-08/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
