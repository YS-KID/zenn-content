---
title: "Codex CLI v0.161 と v0.162 の変更点と既定モデル GPT-6.1 Sol への切り替え"
emoji: "🧭"
type: "tech"
topics: ["codex", "codexcli", "gpt61sol", "configtoml"]
published: false
---

Codex CLI の v0.161.0 と v0.162.0 は、**既定モデルの入れ替え**と**Daybreak の有効化方法の変更**という、設定を触る側に影響する変更を含むリリースです。

結論として、この 2 本で確認すべきことは 2 つです。使うモデルを `config.toml` で固定しているかどうか、そして Daybreak を使っているなら `cli_daybreak` の指定を足したかどうかです。

設定キーは公式の設定リファレンス(2026 年 10 月 12 日取得)で裏を取れた範囲だけを書き、確認できなかったものはその旨を明記します。

> **要点**
> この記事で分かること
>
> - 既定モデルが GPT-6.1 Sol になった範囲と、モデルを固定する書き方
> - Daybreak が明示的な opt-in に変わったこと
> - 承認・サンドボックスの変更と、worktree ツールの位置づけ

## まとめ

- v0.161.0 で既定モデルが GPT-6.1 Sol に。明記されているのは同梱と Amazon Bedrock のカタログで、アカウント側で使えるかは別に確認する
- モデルを固定するなら `config.toml` のトップレベルに `model = "gpt-6.1-sol"`
- Daybreak は `--enable cli_daybreak` か `features.cli_daybreak = true` が必要。`daybreak = true` だけでは効かない
- ripgrep の設定が deny-glob のマスクを弱める問題が修正された。サンドボックスで機密ファイルを除外しているなら上げる価値がある
- `features.cli_daybreak`、worktrees の機能フラグ、`tui.mouse_scroll_speed` は、いずれも公式の設定リファレンスの一覧では確認できなかった

---

設定例・手順の全文はこちらで公開しています: [Codex CLI v0.161 と v0.162 の変更点と既定モデル GPT-6.1 Sol への切り替え](https://aicoding-guide.com/posts/codex-update-0-161/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
