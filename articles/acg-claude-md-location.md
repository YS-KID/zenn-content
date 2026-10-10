---
title: "CLAUDE.md はどこに置くと読まれるのか、ルート・サブディレクトリ・CLAUDE.local.md・--add-dir の違い"
emoji: "🤖"
type: "tech"
topics: ["claudecode", "claudemd", "claudelocalmd", "adddir"]
published: false
---

`CLAUDE.md` を書いたのに効いていない気がする。その原因の大半は内容ではなく「置いた場所が、いま読み込まれる場所ではない」ことです。Claude Code が CLAUDE.md を読む場所は 1 つではなく、読まれるタイミングも場所ごとに違います。

結論として、起動時に読まれるのは「カレントディレクトリから上」にある CLAUDE.md と `~/.claude/CLAUDE.md` です。カレントより下のサブディレクトリのものは Claude がそのディレクトリのファイルを扱ったときに読まれ、`--add-dir` で追加した場所のものは既定では読まれません。

> **要点**
> この記事で分かること
>
> - 起動時に読まれる CLAUDE.md と、あとから読まれる CLAUDE.md の違い
> - モノレポでルートと各パッケージに何を書くか
> - 自分だけのメモを Git に入れずに読ませる CLAUDE.local.md
> - `--add-dir` で追加したディレクトリの CLAUDE.md を読ませる環境変数
> - `/context` と `/memory` の使い分け

## まとめ

- 起動時に読まれるのはカレントディレクトリから上の CLAUDE.md と `~/.claude/CLAUDE.md`。下位のものはそのディレクトリのファイルを扱うときに読まれる
- モノレポではルートに共通事項、各パッケージに固有事項を置き、サブディレクトリはルートと矛盾させない
- 自分だけのメモはルートの `CLAUDE.local.md` に書き、Git 管理から外す。秘密情報は書かない
- `--add-dir` と `permissions.additionalDirectories` はファイルアクセスを付けるだけ。CLAUDE.md を読ませるには `CLAUDE_CODE_ADDITIONAL_DIRECTORIES_CLAUDE_MD` を設定し、信頼できるディレクトリに限る
- 読み込み状況は `/context` の Memory files で確認する

---

設定例・手順の全文はこちらで公開しています: [CLAUDE.md はどこに置くと読まれるのか、ルート・サブディレクトリ・CLAUDE.local.md・--add-dir の違い](https://aicoding-guide.com/posts/claude-md-location/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
