---
title: "Claude Code で npm run 系のコマンドをまとめて許可する書き方"
emoji: "🤖"
type: "tech"
topics: ["claudecode", "allow", "npmrun", "permissions"]
published: true
---

`npm run lint`、`npm run test`、`npm run build` のたびに確認ダイアログが出るのは、Claude Code の作業テンポを落とす最大の要因です。package.json の scripts は自分で書いたコマンドなので、まとめて自動許可にして問題ありません。

結論として、`Bash(npm run:*)` を allow に書けば npm scripts はすべて確認なしになります。`npm install` は別のパターンなので、意図せず許可されることはありません。

> **要点**
> この記事で分かること
>
> - npm / pnpm / yarn / npx の scripts を許可するパターン
> - `:*` の意味と、install 系を巻き込まない書き方
> - Python(pytest、ruff)など他のツールへの応用

## まとめ

- `Bash(npm run:*)` で npm scripts をまとめて許可できる。`npm install` は別パターンなので巻き込まれない
- `npx` や `pnpm` 全体を許可する場合は、install / add 系を ask に入れる(ask が優先される)
- Python なら `pytest`、`ruff`、`uv run` を allow、`pip install` を ask にする

---

設定例・手順の全文はこちらで公開しています: [Claude Code で npm run 系のコマンドをまとめて許可する書き方](https://aicoding-guide.com/posts/claude-code-allow-npm-scripts/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
