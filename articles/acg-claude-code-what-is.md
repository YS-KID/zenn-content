---
title: "Claude Code とは何か、できること・できないことと Cursor や Copilot との違い"
emoji: "🤖"
type: "tech"
topics: ["claudecode"]
published: false
---

Claude Code は、コードベースを読み、ファイルを編集し、コマンドを実行する **エージェント型のコーディングツール** です。公式ドキュメントの説明はこうなっています。

> Claude Code is an agentic coding tool that reads your codebase, edits files, runs commands, and integrates with your development tools.
>
> (Claude Code は、コードベースを読み、ファイルを編集し、コマンドを実行し、開発ツールと連携するエージェント型のコーディングツールです。)

補完を出すだけの道具ではなく、指示を受けて複数ファイルにまたがる作業を自分で進めます。その代わり、どこまで自動で実行させるかを設計する必要があります。この記事では、できることと **仕組みとして保証されないこと** を公式ドキュメントで確認したうえで整理します。

> **要点**
> この記事で分かること
>
> - Claude Code が動く 5 つの場所と、共通する設定
> - できること(作業・連携・拡張)の全体像
> - 「指示」であって強制ではない部分と、強制したいときの手段

## まとめ

- Claude Code はエージェント型のコーディングツールで、ターミナル・VS Code・JetBrains・デスクトップ・Web の 5 つの入口が同じエンジンと設定を共有する
- できることは、実装と修正、git 操作、MCP による外部連携、CLI でのスクリプト化、拡張による自動化
- CLAUDE.md・スキル・出力スタイルは「指示」で、保証はない。例外なく守らせるなら `permissions` とフックを使う
- 作業範囲も文章では狭まらない。起動ディレクトリと deny ルールで決まる
- Cursor や Copilot との比較は、製品カテゴリではなく権限・強制手段・拡張点・動く場所で見る。Cursor の中で Claude Code を動かすこともできる

---

設定例・手順の全文はこちらで公開しています: [Claude Code とは何か、できること・できないことと Cursor や Copilot との違い](https://aicoding-guide.com/posts/claude-code-what-is/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
