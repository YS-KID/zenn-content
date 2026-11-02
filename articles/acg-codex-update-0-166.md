---
title: "Codex CLI v0.166 で追加された codex queue --resume と codex doctor --network-"
emoji: "🧭"
type: "tech"
topics: ["codex", "codexcli", "codexdoctor"]
published: true
---

Codex CLI の v0.166.0 は新機能 6 件、修正 7 件のリリースです。日常の運用に効くのは **`codex queue --resume`** と **`codex doctor --network-only`** の 2 つです。

どちらも既存のコマンドにフラグを足したものです。コマンド本体の挙動を押さえておくと、何が変わったのか分かりやすくなります。

> **要点**
> この記事で分かること
>
> - `codex queue` の使い方と、`--resume` が解決する状況
> - `codex doctor` が調べる範囲と、`--network-only` で絞られる対象
> - 再開とフォークで承認設定とトークン集計が保持されるようになったこと

## まとめ

- `codex queue --resume` で、メッセージをキューに入れたあと読み込まれていないスレッドを再開できる
- `codex queue` は `--thread` に UUID かセッション名を渡し、画像の添付には対応しない
- `codex doctor --network-only` で、設定・接続性・WebSocket に診断を絞れる
- 再開とフォークで、承認設定と推論トークンの集計が保持されるようになった
- `--resume` と `--network-only` は公式のコマンドのドキュメントでは確認できなかった

---

設定例・手順の全文はこちらで公開しています: [Codex CLI v0.166 で追加された codex queue --resume と codex doctor --network-only](https://aicoding-guide.com/posts/codex-update-0-166/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
