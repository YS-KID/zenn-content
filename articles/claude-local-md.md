---
title: "CLAUDE.local.md の使い方:自分だけのメモを Git に入れずに Claude Code に読ませる"
emoji: "🤖"
type: "tech"
topics: ["claudecode", "claudelocalmd", "claudemd"]
published: true
---

チームで共有する `CLAUDE.md` に、自分のローカル環境の DB 名や、個人的に気になっている TODO を書くわけにはいきません。そうした「自分だけが Claude に伝えたいこと」の置き場所が `CLAUDE.local.md` です。

結論として、`CLAUDE.local.md` はプロジェクトのルートに置く Git 管理外のファイルで、`CLAUDE.md` と一緒に自動で読み込まれます。

> **要点**
> この記事で分かること
>
> - CLAUDE.local.md の置き場所と読み込みの仕組み
> - CLAUDE.md との使い分け
> - 書く内容の具体例

## まとめ

- `CLAUDE.local.md` はプロジェクトのルートに置く Git 管理外の個人用メモ。CLAUDE.md と一緒に読み込まれる
- ローカル環境の情報、進行中の作業、個人の好みを書く。チーム規約と矛盾する内容は書かない
- 秘密情報は書かず、環境変数名だけを記す
- `.gitignore` に入っているかを確認する

---

設定例・手順の全文はこちらで公開しています: [CLAUDE.local.md の使い方:自分だけのメモを Git に入れずに Claude Code に読ませる](https://aicoding-guide.com/posts/claude-local-md/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
