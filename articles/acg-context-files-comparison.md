---
title: "CLAUDE.md・AGENTS.md・GEMINI.md の違いは読み込み方だけ、原本 1 つで共通化する"
emoji: "🛠️"
type: "tech"
topics: ["ai", "claudemd", "agentsmd", "geminimd"]
published: false
---

Claude Code、Codex、Gemini CLI を併用すると、それぞれが読むコンテキストファイル(`CLAUDE.md`、`AGENTS.md`、`GEMINI.md`)を用意することになります。同じ内容を 3 か所に書くと、更新のたびにずれていきます。

この記事では、3 つのファイルの仕組みの違いを整理したうえで、**1 つの原本から 3 つのツールに読ませる**構成を紹介します。

> **要点**
> この記事で分かること
>
> - 3 つのファイルの配置場所、階層、読み込みの仕組みの違い
> - 共通化の 3 つの方法(インポート、シンボリックリンク、ファイル名設定)と組み合わせ
> - ツール固有の指示をどこに書くか

## まとめ

- 3 つのファイルは役割も書く内容も同じ。違いは読み込みの仕組みだけ
- AGENTS.md を原本にし、CLAUDE.md は `@AGENTS.md` でインポート、Gemini CLI は `context.fileName` で読ませる
- ツール固有の機能名(Plan Mode、プロファイル名など)は各ツールのファイルに書く
- コピーによる同期は避け、ツール側の参照の仕組みを使う

---

設定例・手順の全文はこちらで公開しています: [CLAUDE.md・AGENTS.md・GEMINI.md の違いは読み込み方だけ、原本 1 つで共通化する](https://aicoding-guide.com/posts/context-files-comparison/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
