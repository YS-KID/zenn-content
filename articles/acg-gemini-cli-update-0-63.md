---
title: "Gemini CLI v0.63 で diff の cannot spawn エラーが修正、変更点は全 15 件"
emoji: "♊"
type: "tech"
topics: ["geminicli", "diff", "settingsjson", "mcp"]
published: false
---

Gemini CLI の v0.63.0 は、**15 件すべてが修正**のリリースです。新しい設定キー、新コマンド、破壊的変更はリリースノートに載っていません。

結論として、このバージョンで価値があるのは 2 件です。diff の実行時に `cannot spawn : No such file or directory` が出ていた原因の削除と、ツール出力の打ち切りが負の値のときに逆に出力を膨らませていた不具合の修正です。

v0.63.0 のリリースノートは **PR のタイトルが並んだ一覧**で、各変更の説明文は付いていません。この記事では個別の PR と公式の設定リファレンスで裏を取れた範囲だけを書き、取れなかったものはその旨を明記します。

> **要点**
> この記事で分かること
>
> - `cannot spawn :` という diff のエラーが出ていた原因と、直ったこと
> - ツール出力の打ち切り設定を 0 以下にしたときの挙動
> - MCP の設定まわりとプラン実行に入った修正

## まとめ

- v0.63.0 は 15 件すべてが修正で、新機能も新しい設定キーもない
- diff で `cannot spawn : No such file or directory` が出ていたのは、Gemini CLI が Git の `diff.external` を空文字で上書きしていたため。v0.63.0 で削除された
- `diff.external` は Git の設定キーで、Gemini CLI の `settings.json` のキーではない
- `tools.truncateToolOutputThreshold` を負の値にすると出力が約 2 倍に膨らむ不具合が直り、0 以下で打ち切りが無効になる
- MCP の有効化設定は `mcp.allowed` / `mcp.excluded` / `admin.mcp.enabled` で、サーバーごとの `enabled` はない

---

設定例・手順の全文はこちらで公開しています: [Gemini CLI v0.63 で diff の cannot spawn エラーが修正、変更点は全 15 件](https://aicoding-guide.com/posts/gemini-cli-update-0-63/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
