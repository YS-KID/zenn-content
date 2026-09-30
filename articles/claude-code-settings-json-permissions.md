---
title: "Claude Code の settings.json で permissions を設計する(allow / deny / ask の実例"
emoji: "🤖"
type: "tech"
topics: ["claudecode", "settingsjson", "permissions"]
published: true
---

Claude Code は既定では、ファイルの編集やコマンドの実行のたびに確認を求めます。安全ではありますが、そのままでは作業のテンポが上がりません。かといって全許可にすると、`rm -rf` や `git push --force` のような取り返しのつかない操作まで自動で通ってしまいます。

この記事では、`settings.json` の `permissions` を使って「安全な操作は自動、危険な操作は確認か禁止」という線引きを作る方法を解説します。

> **要点**
> この記事で分かること
>
> - settings.json の置き場所と優先順位
> - allow / deny / ask の書き方とパターン記法
> - 個人開発・チーム開発それぞれの推奨設定

## まとめ

- 設定はユーザー → プロジェクト → ローカルの順に上書きされ、deny は常に最優先
- `Bash(npm run test:*)` のように「ツール名(パターン)」で書く
- `defaultMode: "acceptEdits"` と少数の allow から始め、危険な操作は deny に入れる
- 対話中に増えた許可は `/permissions` で定期的に見直す

---

設定例・手順の全文はこちらで公開しています: [Claude Code の settings.json で permissions を設計する(allow / deny / ask の実例)](https://aicoding-guide.com/posts/claude-code-settings-json-permissions/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
