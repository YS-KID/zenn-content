---
title: "Claude Code のカスタムスラッシュコマンド(スキル)を作る:繰り返す指示をコマンド化する"
emoji: "🤖"
type: "tech"
topics: ["claudecode"]
published: false
---

「このプロジェクトのルールでコードレビューして」「Conventional Commits 形式でコミットメッセージを書いて」のように、毎回同じ長い指示を打っているなら、それはスラッシュコマンドにする候補です。

Claude Code では、Markdown ファイルを 1 つ置くだけで `/review` や `/commit` のような自分専用のコマンドを定義できます。この記事では、現在の主流である **スキル**形式を中心に、従来の **commands** 形式との関係、引数の扱い、チーム共有の方法をまとめます。

> **要点**
> この記事で分かること
>
> - スキル(SKILL.md)とコマンド(commands/*.md)の違いと使い分け
> - 引数、frontmatter オプション、Bash 実行結果の埋め込み
> - そのまま使えるコマンド例(レビュー、コミット、テスト生成)

## まとめ

- `.claude/skills/<名前>/SKILL.md` を置くだけで `/<名前>` コマンドになる
- `$ARGUMENTS` / `$1` で引数、`` !`コマンド` `` で Bash の実行結果を埋め込める
- `allowed-tools` でコマンド内の自動許可範囲を限定する
- 常時ルールは CLAUDE.md、作業手順はスキル、という分担にする

---

設定例・手順の全文はこちらで公開しています: [Claude Code のカスタムスラッシュコマンド(スキル)を作る:繰り返す指示をコマンド化する](https://aicoding-guide.com/posts/claude-code-custom-slash-commands/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
