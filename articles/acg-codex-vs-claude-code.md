---
title: "Codex と Claude Code の違い:OS サンドボックスかツール単位の許可か、TOML か JSON か"
emoji: "🧭"
type: "tech"
topics: ["codex", "claudecode"]
published: false
---

Codex(OpenAI)と Claude Code(Anthropic)は、どちらもターミナルと VS Code から使えるコーディングエージェントです。「どちらが賢いか」はモデルの更新で頻繁に入れ替わるため、この記事では**変わりにくい部分**、つまり料金体系、権限の考え方、設定ファイル、周辺機能の違いを比較します。

> **要点**
> この記事で分かること
>
> - 料金と契約形態の違い
> - 権限モデル(OS サンドボックス vs ツール単位のルール)の違い
> - 設定ファイル、拡張機能、クラウド実行、CI 連携の違いと使い分けの目安

## まとめ

- 料金はどちらも定額プランの枠か API 従量課金。契約済みの方から試す
- 権限モデルは、Codex が OS サンドボックス、Claude Code がツール単位のルール
- Claude Code は hooks・スキル・サブエージェントで手順を組み込みやすく、Codex は設定がシンプル
- クラウド並列は Codex、GitHub メンション連携は両方可で構成が異なる

---

設定例・手順の全文はこちらで公開しています: [Codex と Claude Code の違い:OS サンドボックスかツール単位の許可か、TOML か JSON か](https://aicoding-guide.com/posts/codex-vs-claude-code/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
