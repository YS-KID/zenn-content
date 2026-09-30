---
title: "Claude Code で git push だけ毎回確認させる ask 設定"
emoji: "🤖"
type: "tech"
topics: ["claudecode", "ask", "gitpush", "permissions"]
published: true
---

「コミットまでは自分で進めてほしいが、push はリモートに影響するので最後に自分で確認したい」。この要望は、`permissions.ask` に `git push` を書くだけで実現できます。

`ask` は「allow に一致していても、必ず確認する」ためのルールです。Git の読み取り系やコミットを allow で自動化しつつ、push だけを止められます。

> **要点**
> この記事で分かること
>
> - `git push` だけ確認させる ask の書き方
> - allow と ask が両方一致したときの優先順位
> - 確認ダイアログの選択肢と、その後の設定への影響

## まとめ

- `permissions.ask` に `Bash(git push:*)` を書くと、push の直前に必ず確認が入る
- ask は allow より優先されるため、Git 操作全体を allow にしていても push は止まる
- 「今後も許可」を選んでも ask が残る限り確認は続く
- ブランチ限定は Claude のコマンドの組み立て方に依存するので、確実さを優先するなら「push は常に確認」に統一する

---

設定例・手順の全文はこちらで公開しています: [Claude Code で git push だけ毎回確認させる ask 設定](https://aicoding-guide.com/posts/claude-code-ask-git-push/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
