---
title: "Claude Code の auto memory を無効にする・保存先を変える設定(autoMemoryEnabled 他)"
emoji: "🤖"
type: "tech"
topics: ["claudecode", "automemory", "automemoryenabled", "automemorydirectory", "settingsjson"]
published: false
---

Claude Code には、あなたが書く CLAUDE.md とは別に、Claude 自身が「指摘されたこと」「好み」「プロジェクトの事情」を書き留めていく **auto memory** があります。便利な反面、共有マシンや検証用の環境では「勝手に何かを覚えてほしくない」「保存先を管理下に置きたい」という要望が出ます。

結論として、`autoMemoryEnabled: false` で無効化、`autoMemoryDirectory` で保存先の変更、`CLAUDE_CODE_DISABLE_AUTO_MEMORY=1` で 1 セッションだけ無効化ができます。

> **要点**
> この記事で分かること
>
> - auto memory が何を、どこに、どこまで保存するか
> - 無効化・保存先変更の 3 つの手段と、それぞれの優先順位
> - 保存された内容の確認と削除の方法

## まとめ

- auto memory は Claude が自分で書く記録で、既定では `~/.claude/projects/<project>/memory/` に保存される
- `autoMemoryEnabled: false` で無効化。プロジェクトの settings に書けばそのプロジェクトだけ止められる
- `CLAUDE_CODE_DISABLE_AUTO_MEMORY=1` は 1 セッション限定で、settings より優先される
- `autoMemoryDirectory` で保存先を変更。プロジェクト設定ではワークスペース信頼が前提
- `MEMORY.md` は先頭 200 行 / 25KB までしか読み込まれない。`/memory` から確認・編集できる

---

設定例・手順の全文はこちらで公開しています: [Claude Code の auto memory を無効にする・保存先を変える設定(autoMemoryEnabled 他)](https://aicoding-guide.com/posts/claude-code-auto-memory-disable/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
