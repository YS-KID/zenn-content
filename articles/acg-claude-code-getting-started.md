---
title: "Claude Code の使い方入門、インストールから最初の 1 時間でやること"
emoji: "🤖"
type: "tech"
topics: ["claudecode", "windows"]
published: true
---

Claude Code を初めて入れるとき、迷いやすいのは「どのインストール方法を選ぶか」と「最初に何を確認すればよいか」の 2 点です。

結論から書くと、インストール方法は **自動更新するかどうか** で選びます。ネイティブインストーラだけが自動更新し、Homebrew・WinGet・Linux のパッケージマネージャは手動更新です。入れたら `claude --version` と `claude doctor` で確認し、それから最初のセッションを始めます。

この記事は 2026 年 10 月 14 日に取得した公式ドキュメントを一次情報としています。Claude Code が何であるかという全体像は [Claude Code とは何か](https://aicoding-guide.com/posts/claude-code-what-is/) にまとめてあるので、ここでは手を動かす順に進めます。

> **要点**
> この記事で分かること
>
> - 動作環境と、Claude Code が使えるプラン
> - インストール方法の選び方(自動更新の有無で決まる)
> - 最初のセッションと、最初の 1 時間で触るべき設定

## まとめ

- 動作環境は macOS 13.0 以降、Windows 10 1809 以降、Ubuntu 20.04 以降など。メモリは 4 GB 以上
- 無料の claude.ai プランでは使えない。Pro・Max・Team・Enterprise か Console、またはクラウドプロバイダ経由
- インストール方法は自動更新の有無で選ぶ。ネイティブと npm は自動更新、Homebrew・WinGet・apt・dnf・apk は手動
- 入れたら `claude --version` で確認し、詰まったら `claude doctor` を読む
- Windows でサンドボックスを使うなら WSL 2。ネイティブ Windows と WSL 1 は非対応
- 最初の 1 時間は、権限モードの確認、`/init`、小さな変更、deny ルールの順で触る

---

設定例・手順の全文はこちらで公開しています: [Claude Code の使い方入門、インストールから最初の 1 時間でやること](https://aicoding-guide.com/posts/claude-code-getting-started/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
