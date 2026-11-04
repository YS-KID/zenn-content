---
title: "Gemini CLI v0.66 は修正のみで keybindings.json の keys 配列とシェル環境の扱いが直った"
emoji: "♊"
type: "tech"
topics: ["geminicli", "keybindingsjson"]
published: false
---

Gemini CLI の v0.66.0 に新機能はありません。リリースノートの「What's Changed」は 26 件すべてが修正・リファクタリング・リリース作業です。

ただし 1 件は、**公式ドキュメントに載っている設定が実際には効いていなかった**という種類の修正です。`keybindings.json` の `keys` 配列が、この版で動くようになりました。

> **要点**
> この記事で分かること
>
> - `keybindings.json` の `keys` 配列の書き方と、割り当てが効かないときの確認方法
> - `.env` の読み込みと設定のプレースホルダの解決順が直ったこと
> - `~/.gitconfig` が保持されるようになったこと

## まとめ

- v0.66.0 に新機能はない。「What's Changed」の 26 件はすべて修正・リファクタリング・リリース作業
- `keybindings.json` の `keys` 配列が効くようになった。解除は `command` の先頭に `-` を付ける
- 割り当てが発火しないときは、ターミナルが送る文字を `Debug Keystroke Logging` と `f12` で確認する
- `.env` の読み込み後に設定のプレースホルダを解決するようになった
- `~/.gitconfig` が保持され、git の対話的なプロンプトは無効になった

---

設定例・手順の全文はこちらで公開しています: [Gemini CLI v0.66 は修正のみで keybindings.json の keys 配列とシェル環境の扱いが直った](https://aicoding-guide.com/posts/gemini-cli-update-0-66/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
