---
title: "Claude Code と git worktree で複数タスクを並列に進める手順"
emoji: "🤖"
type: "tech"
topics: ["claudecode", "gitworktree"]
published: false
---

Claude Code は 1 セッションで 1 つのタスクを進めるのが基本です。「機能 A の実装」と「バグ B の修正」を同時に頼むと、同じ作業ディレクトリ上で変更が混ざり、差分の切り分けが難しくなります。

そこで使うのが **git worktree** です。1 つのリポジトリから複数の作業ディレクトリを作り、それぞれで別のブランチをチェックアウトして、Claude Code を別々に起動します。この記事では、その手順と落とし穴をまとめます。

> **要点**
> この記事で分かること
>
> - git worktree の作り方と Claude Code の起動手順
> - 依存関係、ポート、環境変数の競合を避ける方法
> - 作業後のブランチ統合と worktree の削除

## まとめ

- `git worktree add ../dir -b branch` で作業ディレクトリを増やし、各ディレクトリで `claude` を起動する
- 依存関係のインストール、ポート、`.env` は worktree ごとに用意する
- 同じブランチは 2 か所でチェックアウトできない
- 作業後は `git worktree remove` と `git branch -d` で片付ける

---

設定例・手順の全文はこちらで公開しています: [Claude Code と git worktree で複数タスクを並列に進める手順](https://aicoding-guide.com/posts/claude-code-git-worktree-parallel/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
