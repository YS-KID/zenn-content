---
title: "Claude Code の --add-dir で追加したディレクトリの CLAUDE.md が読まれないときの設定"
emoji: "🤖"
type: "tech"
topics: ["claudecode", "claudemd", "adddir", "additionaldirectories"]
published: false
---

共通の設定やドキュメントを別リポジトリに置き、`claude --add-dir ../shared-config` で参照させている構成はよくあります。ところが、その `shared-config/CLAUDE.md` に書いた指示が効かない、という相談が多い機能です。

結論として、`--add-dir` で追加したディレクトリの CLAUDE.md は **既定では読み込まれません**。環境変数 `CLAUDE_CODE_ADDITIONAL_DIRECTORIES_CLAUDE_MD` を設定したときだけ読み込まれます。

> **要点**
> この記事で分かること
>
> - `--add-dir` が与えるのは「ファイルアクセス」であり「設定の検出」ではないこと
> - `CLAUDE_CODE_ADDITIONAL_DIRECTORIES_CLAUDE_MD` で読み込まれるファイルの範囲
> - `permissions.additionalDirectories` との関係と、毎回付けずに済ませる書き方

## まとめ

- `--add-dir` と `permissions.additionalDirectories` はファイルアクセスを付けるだけで、そこにある CLAUDE.md は既定では読まない
- 読ませるには `CLAUDE_CODE_ADDITIONAL_DIRECTORIES_CLAUDE_MD` を設定する。`CLAUDE.md`、`.claude/CLAUDE.md`、`.claude/rules/*.md`、`CLAUDE.local.md` が対象
- 毎回付けたくなければ settings.json の `env` に書く
- 内容を管理していないディレクトリで有効にしない
- 確認は `/context` の Memory files

---

設定例・手順の全文はこちらで公開しています: [Claude Code の --add-dir で追加したディレクトリの CLAUDE.md が読まれないときの設定](https://aicoding-guide.com/posts/claude-code-add-dir-claude-md/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
