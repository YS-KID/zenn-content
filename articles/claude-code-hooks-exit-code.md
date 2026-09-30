---
title: "Claude Code の hooks の終了コード 0・2・その他の意味と使い分け"
emoji: "🤖"
type: "tech"
topics: ["claudecode", "hooks", "pretooluse", "posttooluse"]
published: false
---

hooks スクリプトの終了コードは、Claude Code に「続けてよいか」「止めるか」「注意だけするか」を伝える信号です。ここを理解していないと、lint が失敗しても Claude が気付かない、あるいは逆に警告のつもりが処理を止めてしまう、といった食い違いが起きます。

結論として、**0 は成功、2 はブロック(標準エラー出力が Claude に渡る)、それ以外は警告(ユーザーに表示、処理は続行)**です。

> **要点**
> この記事で分かること
>
> - 終了コード 0 / 2 / その他の挙動の違い
> - イベント(PreToolUse、PostToolUse など)ごとの「ブロック」の意味
> - JSON 出力による細かい制御

## まとめ

- 終了コード 0 は成功、2 はブロック(標準エラー出力が Claude に渡る)、その他は警告(ユーザーに表示)
- PreToolUse の 2 は実行を中止、PostToolUse の 2 は実行済みの操作に対する修正指示になる
- 人間にだけ知らせたいときは 1、Claude に直させたいときは 2
- 標準出力の JSON で `decision` や `reason` を返すと細かい制御ができる

---

設定例・手順の全文はこちらで公開しています: [Claude Code の hooks の終了コード 0・2・その他の意味と使い分け](https://aicoding-guide.com/posts/claude-code-hooks-exit-code/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
