---
title: "Codex の出力に出るファイル参照を VS Code や Cursor で直接開く file_opener の設定"
emoji: "🧭"
type: "tech"
topics: ["codex", "configtoml", "fileopener", "vscode", "cursor"]
published: false
---

Codex が「`src/auth/session.ts:42` を修正しました」のように場所を示してくれても、そのたびにエディタでファイルを探すのは手間です。Codex CLI には、こうしたファイル参照を **エディタで直接開けるリンク** に変換する `file_opener` 設定があります。

結論として、`~/.codex/config.toml` に `file_opener = "cursor"` のようにエディタ名を書くだけで、出力中のファイル参照がそのエディタの URI スキームのリンクになります。既定は `vscode` です。

> **要点**
> この記事で分かること
>
> - `file_opener` に指定できる 5 つの値と既定
> - リンクが動くために必要なターミナル側の条件
> - 無効化と、SSH 越しなど効かない場面

## まとめ

- `file_opener` はファイル参照をエディタの URI リンクにする設定。値は `vscode`(既定)/ `vscode-insiders` / `windsurf` / `cursor` / `none`
- ターミナルの OSC 8 対応と、エディタの URI スキーム登録が必要
- SSH 先で動かしている Codex のリンクはローカルでは開けない
- IDE 拡張には別の仕組みがあるので、CLI 向けの設定と考える
- 表示まわりは `[tui]` のテーマ・代替スクリーン・アニメーションと組み合わせる

---

設定例・手順の全文はこちらで公開しています: [Codex の出力に出るファイル参照を VS Code や Cursor で直接開く file_opener の設定](https://aicoding-guide.com/posts/codex-file-opener/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
