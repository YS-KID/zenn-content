---
title: "AI コーディングツールに API キーや秘密情報を読ませないための設定:Claude Code・Codex・Gemini CLI 共通の対"
emoji: "🛠️"
type: "tech"
topics: ["ai", "env", "claudecode", "codex", "geminicli"]
published: true
---

コーディングエージェントは、指示を実行するために必要だと判断すれば `.env` や `config/secrets.yml` を読みます。読んだ内容は API に送信され、ログや履歴に残ります。「.gitignore に入れているから大丈夫」は誤りで、エージェントの読み取りと Git の管理対象は別の話です。

この記事では、Claude Code・Codex・Gemini CLI それぞれで秘密情報の読み取りを防ぐ設定と、ツールに依存しない根本対策をまとめます。

> **要点**
> この記事で分かること
>
> - 3 ツールそれぞれで `.env` などの読み取りを禁止する設定
> - MCP サーバー・hooks・CI での漏えい経路と対策
> - 秘密情報をリポジトリに置かない構成と、読ませてしまった後の対処

## まとめ

- `.gitignore` はエージェントの読み取りを防がない。ツールごとの除外設定が必要
- Claude Code は `deny` の `Read(...)`、Codex は配置と AGENTS.md、Gemini CLI は `.geminiignore` と GEMINI.md
- 根本対策は「読める場所に置かない」。`.env.example` とシークレットマネージャーを使う
- 読ませてしまったら、失効・再発行が唯一の確実な対処

---

設定例・手順の全文はこちらで公開しています: [AI コーディングツールに API キーや秘密情報を読ませないための設定:Claude Code・Codex・Gemini CLI 共通の対策](https://aicoding-guide.com/posts/ai-coding-security-secrets/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
