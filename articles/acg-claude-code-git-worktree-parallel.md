---
title: "Claude Code と git worktree で複数タスクを並列に進める手順"
emoji: "🤖"
type: "tech"
topics: ["claudecode", "gitworktree"]
published: false
---

Claude Code は 1 セッションで 1 つのタスクを進めるのが基本です。「機能 A の実装」と「バグ B の修正」を同時に頼むと、同じ作業ディレクトリ上で変更が混ざり、差分の切り分けが難しくなります。

そこで使うのが **git worktree** です。同じリポジトリの履歴とリモートを共有しながら、ファイルとブランチだけを別に持つ作業ディレクトリです。Claude Code には worktree を作ってその中でセッションを開始する起動オプションがあるため、git のコマンドを自分で打つ必要はほとんどありません。

> **要点**
> この記事で分かること
>
> - `--worktree` での隔離セッションの起動と、Git 管理外のファイルの持ち込み
> - メインのチェックアウトへの操作をブロックする隔離チェックの内容
> - 終了時の後片付けと、worktree が残る条件

## まとめ

- `claude --worktree <名前>` で `.claude/worktrees/` 配下に worktree を作り、その中でセッションが始まる
- worktree は新規のチェックアウト。依存関係はその場で入れ、`.env` は `.worktreeinclude` で持ち込む
- 隔離チェックは編集・作業ディレクトリ・git のリダイレクトを止めるが、単純な `cp` は止めない
- `.git`、プロジェクトのプラグイン、権限の承認はメインのチェックアウトと共有される
- 対話セッションの終了時に、作業が残っている worktree の扱いを確認される。`-p` 実行では残る

---

設定例・手順の全文はこちらで公開しています: [Claude Code と git worktree で複数タスクを並列に進める手順](https://aicoding-guide.com/posts/claude-code-git-worktree-parallel/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
