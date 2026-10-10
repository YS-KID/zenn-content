---
title: "Claude Code の settings.json と settings.local.json で permissions を設計する"
emoji: "🤖"
type: "tech"
topics: ["claudecode", "settingsjson", "settingslocaljson", "permissions"]
published: false
---

Claude Code は既定では、ファイルの編集やコマンドの実行のたびに確認を求めます。安全ではありますが、そのままでは作業のテンポが上がりません。かといって全許可にすると、`rm -rf` や `git push --force` のような取り返しのつかない操作まで自動で通ってしまいます。

この記事では、`settings.json` の `permissions` を使って「安全な操作は自動、危険な操作は確認か禁止」という線引きを作る方法と、チームで共有する `settings.json` と個人用の `settings.local.json` の役割分担を解説します。

> **要点**
> この記事で分かること
>
> - settings.json の置き場所と優先順位
> - allow / deny / ask の書き方とパターン記法
> - 個人用の settings.local.json に何が書き込まれ、どう Git 管理から外れるか
> - 個人開発・チーム開発それぞれの推奨設定

## まとめ

- 設定はユーザー → プロジェクト → ローカルの順に上書きされ、permissions の deny は常に最優先
- `Bash(npm run test:*)` のように「ツール名(パターン)」で書く
- `settings.json` はチーム共有(Git 管理)、`settings.local.json` は個人用。「今後も許可」はローカルの allow に追記されるので `/permissions` で定期的に見直す
- `settings.local.json` はリポジトリの `.gitignore` ではなくグローバルの git 除外設定で外れる。全員に効かせるなら `.gitignore` にも書く
- `defaultMode: "acceptEdits"` と少数の allow から始め、危険な操作は deny に入れる

---

設定例・手順の全文はこちらで公開しています: [Claude Code の settings.json と settings.local.json で permissions を設計する](https://aicoding-guide.com/posts/claude-code-settings-json-permissions/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
