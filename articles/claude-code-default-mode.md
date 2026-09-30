---
title: "Claude Code の権限モード 6 種類の違いと選び方(defaultMode の設定)"
emoji: "🤖"
type: "tech"
topics: ["claudecode", "defaultmode", "acceptedits", "permissions"]
published: true
---

Claude Code の `permissions.defaultMode` は、「allow にも deny にも一致しなかった操作をどう扱うか」を決める設定です。指定できる値は **6 つ**あります。

結論として、個人開発なら `acceptEdits`、初めて触るコードベースや設計作業なら `plan`、CI で許可リストを厳密にするなら `dontAsk`、隔離環境だけ `bypassPermissions` が目安です。

> **要点**
> この記事で分かること
>
> - 6 つのモードの違い(何が自動で、何が確認されるか)
> - セッションの開始モードが決まる順序
> - プロジェクト設定では効かない 2 つの値

## まとめ

- モードは 6 種類。`default`(Manual)・`acceptEdits`・`plan`・`auto`・`dontAsk`・`bypassPermissions`
- deny はすべてのモードで効き、allow は `bypassPermissions` では効果がない
- Pro・Max・Team プランの開始モードは auto。フラグ → `defaultMode` → 組み込みの既定値の順で決まる
- `auto` と `bypassPermissions` は `.claude/settings.json` と `.claude/settings.local.json` では効かない
- `Shift+Tab` と `--permission-mode` は一時的な切り替えで、設定ファイルは変わらない

---

設定例・手順の全文はこちらで公開しています: [Claude Code の権限モード 6 種類の違いと選び方(defaultMode の設定)](https://aicoding-guide.com/posts/claude-code-default-mode/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
