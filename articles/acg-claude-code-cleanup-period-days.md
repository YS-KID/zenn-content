---
title: "Claude Code のトランスクリプトはいつ消えるか:cleanupPeriodDays の既定値と保持期間の変え方"
emoji: "🤖"
type: "tech"
topics: ["claudecode", "cleanupperioddays", "settingsjson"]
published: true
---

Claude Code は、会話のすべて(メッセージ、ツール呼び出し、ツールの結果)を `~/.claude/projects/<project>/<session>.jsonl` に **平文** で保存します。ツールが `.env` を読めばその中身が、コマンドがトークンを出力すればその値が、そのままファイルに残ります。

結論として、保持期間は settings.json の `cleanupPeriodDays` で決まり、既定は 30 日です。短くすれば露出を減らせ、書き込み自体を止める手段もあります。

> **要点**
> この記事で分かること
>
> - `cleanupPeriodDays` の既定値・最小値と、0 が使えない理由
> - 自動削除の対象になるファイルと、ならないファイル
> - トランスクリプトをそもそも書かせない方法と、1 プロジェクト分をまとめて消すコマンド

## まとめ

- トランスクリプトは `~/.claude/projects/` に平文で保存され、`cleanupPeriodDays`(既定 30 日、最小 1)を過ぎると削除される
- `0` は設定できない。長期保持は `3650` のような大きな値で
- `history.jsonl`、auto memory、Desktop/Cowork のセッションはスイープの対象外(Desktop は別キーで上限を付ける)
- 書き込み自体を止めるなら `CLAUDE_CODE_SKIP_PROMPT_HISTORY=1`、非対話なら `--no-session-persistence`
- 認証情報は deny 設定で最初から読ませない。`claude project purge` で 1 プロジェクト分を削除できる

---

設定例・手順の全文はこちらで公開しています: [Claude Code のトランスクリプトはいつ消えるか:cleanupPeriodDays の既定値と保持期間の変え方](https://aicoding-guide.com/posts/claude-code-cleanup-period-days/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
