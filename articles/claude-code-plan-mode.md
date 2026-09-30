---
title: "Claude Code の Plan Mode の使い方:実装前に計画を確認してから作業させる"
emoji: "🤖"
type: "tech"
topics: ["claudecode", "planmode"]
published: false
---

「リファクタリングして」と頼んだら、想定と違う方向に大量のファイルが書き換えられていた。Claude Code を使っていると一度は経験する手戻りです。これを防ぐのが **Plan Mode** です。

Plan Mode では Claude はファイルを読んで調査し、実装計画を提示するところまでで止まります。計画を確認して修正したうえで実装に移せるため、大きめの変更ほど効果があります。

> **要点**
> この記事で分かること
>
> - Plan Mode への入り方と、通常モード・acceptEdits との違い
> - 計画を確認して実装に進むまでの流れ
> - Plan Mode を使うべき場面と、使わなくてよい場面

## まとめ

- Plan Mode は読み取り専用で、調査と計画提示までを行うモード
- `Shift+Tab`、`--permission-mode plan`、`defaultMode: "plan"` の 3 通りで入れる
- 複数ファイルにまたがる変更や設計判断が必要な作業で使い、小さな修正では使わない
- 指示は「目的・制約・求める出力」を分けて書くと計画の質が上がる

---

設定例・手順の全文はこちらで公開しています: [Claude Code の Plan Mode の使い方:実装前に計画を確認してから作業させる](https://aicoding-guide.com/posts/claude-code-plan-mode/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
