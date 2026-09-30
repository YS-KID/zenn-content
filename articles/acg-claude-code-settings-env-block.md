---
title: "Claude Code の settings.json の env キーで環境変数を固定する:シェルより優先される仕組みと書き方"
emoji: "🤖"
type: "tech"
topics: ["claudecode", "settingsjson", "env"]
published: false
---

`ANTHROPIC_MODEL` や `BASH_DEFAULT_TIMEOUT_MS` のような Claude Code の環境変数を、`.bashrc` や `.zshrc` に書くと、IDE 拡張やデスクトップアプリから起動したときに効かないことがあります。起動経路によってシェルの初期化が走らないためです。

結論として、settings.json の `env` キーに書けば、Claude Code がファイルから直接読むため **起動方法に関係なく** すべてのセッションとサブプロセスに適用され、シェルで設定した同名の変数より優先されます。

> **要点**
> この記事で分かること
>
> - `env` キーの書き方と、どのファイルに書くと誰に効くか
> - シェルの環境変数・複数の settings ファイル間の優先順位
> - 保存した値が実行中のセッションに反映される条件と、反映されないケース

## まとめ

- `env` に書いた変数は起動方法に関係なく、すべてのセッションとサブプロセスに適用される
- シェルの同名変数より settings の値が優先される。settings ファイル間は通常の優先順位に従う
- 保存後、追加と変更は実行中のセッションに反映されるが、起動時にだけ読む機能と削除は再起動まで反映されない
- 共有される `.claude/settings.json` に秘密情報を書かない
- 値は文字列で書く

---

設定例・手順の全文はこちらで公開しています: [Claude Code の settings.json の env キーで環境変数を固定する:シェルより優先される仕組みと書き方](https://aicoding-guide.com/posts/claude-code-settings-env-block/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
