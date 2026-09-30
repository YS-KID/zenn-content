---
title: "Claude Code で他チームの CLAUDE.md を読み込ませない claudeMdExcludes の設定"
emoji: "🤖"
type: "tech"
topics: ["claudecode", "claudemd", "claudemdexcludes", "settingsjson"]
published: false
---

大きなモノレポで `claude` を起動すると、リポジトリのルートや他チームのディレクトリに置かれた `CLAUDE.md` まで読み込まれ、自分の作業に関係ない指示がコンテキストに混ざることがあります。Claude Code はカレントディレクトリから上位に向かって CLAUDE.md を探すため、これは仕様どおりの動作です。

結論として、`settings.json` の `claudeMdExcludes` に除外したいファイルのパスかグロブパターンを書くと、そのファイルだけをメモリの読み込みから外せます。

> **要点**
> この記事で分かること
>
> - `claudeMdExcludes` の書き方と、パターンが「絶対パス」に対して照合されること
> - どの settings ファイルに書くべきか、複数の層に書いたときの扱い
> - 除外できないファイル(管理ポリシー)と、効いているかの確認方法

## まとめ

- モノレポでは上位や他チームの CLAUDE.md が読み込まれるのが仕様。`claudeMdExcludes` で特定ファイルだけ外せる
- パターンは絶対パスに対して照合される。`**/` で前方を受けるか、フルパスで書く
- 自分だけの除外は `.claude/settings.local.json` に書く。層をまたぐ配列はマージされる
- 管理ポリシーの CLAUDE.md と `claudeMd` キーの指示は除外できない
- 確認は `/context` の Memory files 一覧

---

設定例・手順の全文はこちらで公開しています: [Claude Code で他チームの CLAUDE.md を読み込ませない claudeMdExcludes の設定](https://aicoding-guide.com/posts/claude-code-claude-md-excludes/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
