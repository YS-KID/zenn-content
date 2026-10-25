---
title: "Codex CLI v0.164 で追加された /presets と /permissions の引数指定と権限プロファイル"
emoji: "🧭"
type: "tech"
topics: ["codex", "codexcli"]
published: false
---

Codex CLI の v0.164.0 は、ここ数バージョンでは珍しく新機能が複数入ったリリースです。中心は **`/presets`** と、**`/permissions` の引数指定**です。

後者は単なる入力の短縮ではありません。背後にあるのは **権限プロファイル** という beta の仕組みで、従来の `sandbox_mode` とは併用できません。これを知らずに設定すると、意図した側が無視されます。

> **要点**
> この記事で分かること
>
> - `/presets` の 10 枠に何を保存できるか
> - `/permissions` が切り替える権限プロファイルの組み立て方
> - 権限プロファイルと `sandbox_mode` を併用できない理由

## まとめ

- `/presets` で、再利用するプロンプトとスラッシュコマンドを番号付きの 10 枠に保存できる
- `/model` と `/permissions` が引数での直接指定に対応した
- `/permissions` が選ぶ権限プロファイルは beta の機能で、組み込みは `:read-only` / `:workspace` / `:danger-full-access` の 3 つ
- 権限プロファイルと `sandbox_mode` は併用できない。`sandbox_mode` が残っているとそちらが使われる
- `/presets` と `/permissions` は公式のスラッシュコマンド一覧では確認できなかった

---

設定例・手順の全文はこちらで公開しています: [Codex CLI v0.164 で追加された /presets と /permissions の引数指定と権限プロファイル](https://aicoding-guide.com/posts/codex-update-0-164/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
