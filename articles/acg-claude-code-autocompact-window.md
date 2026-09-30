---
title: "Claude Code の自動コンパクトを早める・止める設定:/autocompact と CLAUDE_AUTOCOMPACT_PCT_O"
emoji: "🤖"
type: "tech"
topics: ["claudecode", "autocompact"]
published: false
---

長いセッションで「気づいたら会話が要約されていて、直前の指示が薄れた」という経験は多いはずです。逆に、コンテキストが埋まりきる前に早めに要約させて、性能の低下を避けたい場面もあります。

結論として、自動コンパクトが走る「ウィンドウの大きさ」は `/autocompact`、`--autocompact` フラグ、`CLAUDE_CODE_AUTO_COMPACT_WINDOW` の 3 か所で設定でき、そのウィンドウの何 % で走らせるかは `CLAUDE_AUTOCOMPACT_PCT_OVERRIDE` で早められます。完全に止めるなら `autoCompactEnabled: false` です。

> **要点**
> この記事で分かること
>
> - 既定で自動コンパクトが走るタイミング(モデルによって違う)
> - ウィンドウを変える 3 つの手段と、その優先順位
> - しきい値を「早める」専用の環境変数と、無効化の方法

## まとめ

- 既定では会話がモデルの上限に達したときにコンパクトする。1M モデルは約 967K、200K モデルは 200K が境界
- ウィンドウは `/autocompact`(保存)、`--autocompact`(1 回)、`CLAUDE_CODE_AUTO_COMPACT_WINDOW`(最優先)で変える。100K〜1M
- `CLAUDE_AUTOCOMPACT_PCT_OVERRIDE` はウィンドウの何 % で走らせるかを指定し、早める方向にしか効かない
- `autoCompactEnabled: false` で自動コンパクトを無効化。手動の `/compact` は使える
- 止めるなら焦点付きの `/compact` と `/clear` を習慣にする

---

設定例・手順の全文はこちらで公開しています: [Claude Code の自動コンパクトを早める・止める設定:/autocompact と CLAUDE_AUTOCOMPACT_PCT_OVERRIDE](https://aicoding-guide.com/posts/claude-code-autocompact-window/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
