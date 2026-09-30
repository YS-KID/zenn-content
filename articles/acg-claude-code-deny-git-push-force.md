---
title: "Claude Code で git push --force を禁止する deny 設定"
emoji: "🤖"
type: "tech"
topics: ["claudecode", "deny", "gitpushforce", "permissions"]
published: false
---

Claude Code に Git 操作を任せていると、コンフリクトの解消中に `git push --force` を実行されて、他の人のコミットが消える事故が起こり得ます。これを防ぐには、`settings.json` の `permissions.deny` に force push のパターンを書いておきます。

結論として、次の 4 行をプロジェクトの `.claude/settings.json` に入れておけば、Claude Code は force push を実行できなくなります。

> **要点**
> この記事で分かること
>
> - force push を禁止する deny の書き方
> - `-f` や `--force-with-lease` など表記の揺れへの対処
> - 設定が効いているかの確認方法

## まとめ

- `.claude/settings.json` の `permissions.deny` に `Bash(git push --force:*)` などの 4 行を書く
- deny は前方一致なので、`-f`、`--force-with-lease`、オプション順の違いを個別に書く
- deny は allow より常に優先され、個人設定で解除できない
- 確実に守るにはリモートのブランチ保護を併用する

---

設定例・手順の全文はこちらで公開しています: [Claude Code で git push --force を禁止する deny 設定](https://aicoding-guide.com/posts/claude-code-deny-git-push-force/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
