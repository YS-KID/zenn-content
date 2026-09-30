---
title: "Claude Code の Bash は既定 2 分で打ち切られる:BASH_DEFAULT_TIMEOUT_MS で延ばす"
emoji: "🤖"
type: "tech"
topics: ["claudecode", "bash", "settingsjson"]
published: false
---

テストスイートやビルドを Claude に実行させると、2 分で「タイムアウト」になって結果を見てもらえない。あるいは長いログの後半が切れて、Claude が肝心のエラーを見落とす。どちらも Claude Code の Bash ツールに既定の上限があるために起きます。

結論として、タイムアウトは `BASH_DEFAULT_TIMEOUT_MS` と `BASH_MAX_TIMEOUT_MS`、出力の上限は `bashOutputMaxChars`(または `BASH_MAX_OUTPUT_LENGTH`)で調整します。settings.json の `env` に書けば毎回付ける必要はありません。

> **要点**
> この記事で分かること
>
> - タイムアウトを決める 2 つの環境変数と、その関係
> - 出力上限を決める設定キーと環境変数、どちらが優先されるか
> - settings.json への書き方と、作業ディレクトリが戻らない問題の対処

## まとめ

- 既定のタイムアウトは 2 分(`BASH_DEFAULT_TIMEOUT_MS`)、モデルが指定できる上限は 10 分(`BASH_MAX_TIMEOUT_MS`)。実効上限は両者の大きい方
- 出力は既定 30,000 文字まで。超えた分はファイルに保存される。`bashOutputMaxChars`(4,000〜128,000)で調整し、設定すると `BASH_MAX_OUTPUT_LENGTH` は無視される
- settings.json の `env` に書けばシェルより優先され、毎回付けなくてよい
- 終わらないコマンドはタイムアウト延長ではなくバックグラウンド実行にする
- `cd` でディレクトリがずれるなら `CLAUDE_BASH_MAINTAIN_PROJECT_WORKING_DIR`

---

設定例・手順の全文はこちらで公開しています: [Claude Code の Bash は既定 2 分で打ち切られる:BASH_DEFAULT_TIMEOUT_MS で延ばす](https://aicoding-guide.com/posts/claude-code-bash-timeout-env/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
