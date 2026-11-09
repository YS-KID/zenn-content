---
title: "Codex CLI v0.167 で追加された codex agents と自動圧縮の修正"
emoji: "🧭"
type: "tech"
topics: ["codex", "codexcli", "codexagents"]
published: true
---

Codex CLI の v0.167.0 は、新機能 6 件・修正 6 件・ドキュメント 2 件・雑務 2 件のリリースです。日常の作業に効くのは **agent command center まわりの強化**と、**自動コンテキスト圧縮のトークン計算の修正**の 2 つです。

ただしこのリリースには、リリースノートと公式ドキュメントが正面から食い違っている箇所があります。先にそこを押さえておくと、コマンドが動かないときに迷いません。

> **要点**
> この記事で分かること
>
> - `codex agents` が開く agent command center と、`--no-daemon` を付けてよいのかどうか
> - 自動コンテキスト圧縮が何を数えるようになったのか、しきい値をどこで変えるのか
> - Vertex AI 設定とシステムプロキシの追加分が、まだ設定リファレンスに載っていないこと

## まとめ

- v0.167.0 の目玉は agent command center の未読表示と、バックエンド切り替え時の下書き保持
- `codex agents` は Stable のコマンドだが、公式ドキュメントは `--no-daemon` との併用を否定している。リリースノートとは食い違っており、どちらが実装かは確認できなかった
- 自動コンテキスト圧縮が、失敗レスポンスの残存出力とトークン使用量不明のレスポンスを数えるようになった
- 圧縮のしきい値は `model_auto_compact_token_limit` と `model_auto_compact_token_limit_scope` で調整する
- `gcp_setup_wizard` とシステムプロキシの設定は、確認した 2 ページの設定リファレンスには載っていない

---

設定例・手順の全文はこちらで公開しています: [Codex CLI v0.167 で追加された codex agents と自動圧縮の修正](https://aicoding-guide.com/posts/codex-update-0-167/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
