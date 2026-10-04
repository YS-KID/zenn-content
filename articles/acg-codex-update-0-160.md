---
title: "Codex CLI v0.160 の変更点と自動レビュー(Guardian)の設定"
emoji: "🧭"
type: "tech"
topics: ["codex", "codexcli", "guardian"]
published: false
---

Codex CLI の v0.160.0 は、バグ修正が多くを占めるなかで **自動レビュー(Guardian)がオプトインで拡張された** リリースです。

結論として、設定として触れる価値があるのは Guardian の方針です。`config.toml` の `auto_review.policy` にレビュー方針を Markdown で書き、組織で統一するなら管理設定の `guardian_policy_config` を使います。

この記事はリリースノートを一次情報とし、設定キーは公式の設定リファレンスで裏を取った範囲だけを書きます。確認できなかったものはその旨を明記します。

> **要点**
> この記事で分かること
>
> - v0.160.0 の新機能 4 件
> - `auto_review.policy` と管理設定 `guardian_policy_config` の関係
> - 設定リファレンスでまだ確認できないもの

## まとめ

- v0.160.0 の新機能は 4 件。設定で制御できるのは自動レビュー(Guardian)だけ
- 方針は `auto_review.policy` に Markdown で書き、補足は `auto_review.extra_policy`
- 管理設定の `guardian_policy_config` と `guardian_extra_policy` がローカル設定より優先される
- 空文字列は無視されるため、方針を外すときはキーごと消す
- 「ワークスペースの既定」と TUI のコピー設定のキーは、2026 年 10 月 5 日時点の設定リファレンスでは確認できなかった

---

設定例・手順の全文はこちらで公開しています: [Codex CLI v0.160 の変更点と自動レビュー(Guardian)の設定](https://aicoding-guide.com/posts/codex-update-0-160/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
