---
title: "Claude Code の settings.local.json とは:settings.json との違いと .gitignore の扱"
emoji: "🤖"
type: "tech"
topics: ["claudecode", "settingslocaljson", "settingsjson", "gitignore", "permissions"]
published: false
---

`.claude/` ディレクトリを見ると、`settings.json` のほかに `settings.local.json` というファイルができていることがあります。これは Claude Code が自動生成する**個人用の設定ファイル**で、チームで共有する `settings.json` とは役割が違います。

結論として、`settings.json` は Git で共有するチームのルール、`settings.local.json` は Git に入れない自分専用の追加設定です。

> **要点**
> この記事で分かること
>
> - settings.json と settings.local.json の役割と優先順位
> - 「今後も許可」が settings.local.json に追記される仕組み
> - どちらに何を書くべきかの切り分け

## まとめ

- `settings.json` はチーム共有(Git 管理)、`settings.local.json` は個人用(Git 管理外)
- 「今後も許可」は `settings.local.json` の allow に追記される。`/permissions` で定期的に見直す
- 優先順位は管理者設定 > コマンドライン(`--settings`)> ローカル > プロジェクト > ユーザー。permissions は deny → ask → allow の順に評価されるため、プロジェクトの deny をローカルの allow で解除できない
- チームの設定は慎重側に、個人の高速化はローカルで上書きする

---

設定例・手順の全文はこちらで公開しています: [Claude Code の settings.local.json とは:settings.json との違いと .gitignore の扱い](https://aicoding-guide.com/posts/claude-code-settings-local-json/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
