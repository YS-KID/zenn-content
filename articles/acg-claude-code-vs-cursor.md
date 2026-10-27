---
title: "Claude Code と Cursor の違いを料金・権限設定・ルールファイルで比較する"
emoji: "🤖"
type: "tech"
topics: ["claudecode", "cursor"]
published: false
---

Claude Code(Anthropic)と Cursor は、どちらもコーディングエージェントです。Cursor はエディタとして知られていますが、現在は CLI も提供していて、ターミナルでの使い方は Claude Code に近づいています。

一方で、**料金に何が含まれるか**は 2026 年に大きく変わりました。Cursor は X Subscription の一部として売られ、契約に含まれるのは Grok と Composer です。Claude のモデルを使うには別料金がかかります。ここが使い分けを決める最大の分かれ目です。

> **要点**
> この記事で分かること
>
> - 料金に含まれるモデルが根本的に違うこと
> - 権限の書き方は似ているが、設定を置ける場所が違うこと
> - プロジェクトのルールファイルの作法の違い

## まとめ

- Cursor は X Subscription の一部として売られ、含まれるのは Grok 4.7 / 4.6 / 4.5 と Composer 2.5
- サードパーティのモデルは契約に含まれず、Premium 以上で API の定価を前払いクレジットから払う。Plus では使えない
- Claude Code は Pro(月 20 ドル)と Max(100 ドルから)に含まれ、Free では使えない
- 権限の記法は似ているが、Cursor はプロジェクト単位で権限しか設定できない
- Cursor の `.cursor/rules` では `.md` は無視される。`.mdc` か `AGENTS.md` を使う

---

設定例・手順の全文はこちらで公開しています: [Claude Code と Cursor の違いを料金・権限設定・ルールファイルで比較する](https://aicoding-guide.com/posts/claude-code-vs-cursor/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
