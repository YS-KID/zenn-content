---
title: "Windows で Claude Code を使う:ネイティブ版と WSL の違い、インストール手順とつまずきポイント"
emoji: "🤖"
type: "tech"
topics: ["claudecode", "windows", "wsl", "powershell"]
published: false
---

Claude Code は当初 macOS と Linux が主な対象で、Windows では WSL(Windows Subsystem for Linux)経由の利用が案内されていました。現在は **Windows ネイティブ版**が提供され、PowerShell からそのまま使えます。ただし、Git for Windows が必要であること、hooks やスクリプトの書き方が Unix 前提であることなど、知っておくべき違いがあります。

この記事では、ネイティブ版と WSL 版の比較、それぞれの手順、実際につまずきやすい点をまとめます。

> **要点**
> この記事で分かること
>
> - ネイティブ版と WSL 版の違いと選び方
> - それぞれのインストール手順と VS Code 拡張との組み合わせ
> - パス、日本語入力、hooks に関するつまずきポイント

## まとめ

- Windows ネイティブ版は Git for Windows が前提。PowerShell から `irm https://claude.ai/install.ps1 | iex` で入る
- Linux 向けツールチェーンを使うなら WSL 版。プロジェクトは WSL 内に置く
- hooks やスクリプトは Git Bash 上で動く前提で書き、改行コードは LF にする
- 日本語入力や文字化けは Windows Terminal と UTF-8 設定、または VS Code 拡張で回避する

---

設定例・手順の全文はこちらで公開しています: [Windows で Claude Code を使う:ネイティブ版と WSL の違い、インストール手順とつまずきポイント](https://aicoding-guide.com/posts/claude-code-windows-setup/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
