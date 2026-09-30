---
title: "Claude Code の PreToolUse フックで rm -rf を止める設定と、その限界"
emoji: "🤖"
type: "tech"
topics: ["claudecode", "hooks", "pretooluse", "rmrf"]
published: true
---

`rm -rf` のような取り返しのつかないコマンドだけは、確認を挟まずに実行されると困ります。`PreToolUse` フックを使うと、ツール呼び出しの直前にスクリプトで判定して拒否できます。

このフックの強みは、**権限モードより先に発火する**ことです。公式ドキュメントは、`PreToolUse` フックが `dontAsk` を含むすべての権限モードで権限チェックより先に発火し、`permissionDecision: "deny"` を返せば `bypassPermissions` や `--dangerously-skip-permissions` でもツールをブロックすると明記しています。

> **要点**
> この記事で分かること
>
> - 終了コード 2 と `permissionDecision` の 2 通りの止め方
> - 権限モードを変えても迂回されない理由と、逆にできないこと
> - 文字列一致の限界と、併用すべき設定

## まとめ

- `PreToolUse` フックは権限チェックより先に発火し、`deny` は `bypassPermissions` でも効く
- 止め方は 2 通り。短く書くなら `exit 2`、理由を渡すなら `permissionDecision` の JSON
- 同じイベントに複数のフックを並べると並列実行され、拒否が優先される
- フックの `allow` では deny ルールを上書きできない。強められるが緩められない
- 文字列一致は `rm -r -f` や変数展開で外れる。確実な遮断は deny ルールとサンドボックスに任せる

---

設定例・手順の全文はこちらで公開しています: [Claude Code の PreToolUse フックで rm -rf を止める設定と、その限界](https://aicoding-guide.com/posts/claude-code-hooks-block-rm/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
