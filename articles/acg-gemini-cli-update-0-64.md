---
title: "Gemini CLI v0.64 で @ を含むコードを渡すと固まる不具合と headless の信頼状態が修正"
emoji: "♊"
type: "tech"
topics: ["geminicli", "headless"]
published: false
---

Gemini CLI の v0.64.0 には新機能がありません。リリースノートの「What's Changed」は 17 件すべてが修正・リファクタリング・リリース作業です。

ただし、そのうち 2 件は実害の大きい不具合の修正です。**`@` を含むコードを `-p` に流すと CPU 100% のまま固まる**問題と、**headless モードで未信頼のフォルダが信頼済みとして扱われる**問題です。前者に心当たりがあるなら、更新する理由になります。

> **要点**
> この記事で分かること
>
> - `@scope/pkg` のようなコードを渡すと固まっていた原因と、効いていた回避策
> - headless モードのフォルダ信頼が実際の判定とずれていた問題
> - ファイル書き込みと状態保存が atomic になったこと

## まとめ

- v0.64.0 に新機能はない。「What's Changed」の 17 件はすべて修正・リファクタリング・リリース作業
- `@scope/pkg` を含むコードを `-p` に流すと CPU 100% で固まる不具合が修正された。SIGKILL でしか止まらなかった
- headless モードで未信頼のフォルダが信頼済みとして扱われる問題が修正された
- ファイル書き込みと状態保存が atomic になり、状態が壊れたときはバックアップから復旧する
- `security.folderTrust.enabled` の既定値は、公式ドキュメント内で `true` と「disabled by default」に食い違っている

---

設定例・手順の全文はこちらで公開しています: [Gemini CLI v0.64 で @ を含むコードを渡すと固まる不具合と headless の信頼状態が修正](https://aicoding-guide.com/posts/gemini-cli-update-0-64/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
