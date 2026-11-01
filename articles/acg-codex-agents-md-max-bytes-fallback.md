---
title: "Codex の AGENTS.md は既定で 32 KiB までしか読まれない:project_doc_max_bytes の設定"
emoji: "🧭"
type: "tech"
topics: ["codex", "agentsmd", "projectdocmaxbytes", "configtoml"]
published: true
---

AGENTS.md に細かく書いたのに、後半の指示が効いていない。あるいは、チームが `CLAUDE.md` や `TEAM_GUIDE.md` で運用していて Codex 用に別ファイルを増やしたくない。どちらも Codex の AGENTS.md の読み込みルールを知ると解決します。

結論として、Codex は AGENTS.md をルートからカレントディレクトリに向かって連結し、**合計 32 KiB(既定)** に達したところで読み込みを止めます。上限は `project_doc_max_bytes` で、代替ファイル名は `project_doc_fallback_filenames` で変えられます。

> **要点**
> この記事で分かること
>
> - AGENTS.md の探索順(グローバル → プロジェクト)と `AGENTS.override.md` の役割
> - 既定 32 KiB の上限がどう効くかと、`project_doc_max_bytes` の変え方
> - `project_doc_fallback_filenames` で `CLAUDE.md` などを代わりに読ませる方法

## まとめ

- AGENTS.md は `~/.codex/` → Git ルート → カレントディレクトリ の順に集められ、ルート側から連結される。カレントより下は読まれない
- 各階層で `AGENTS.override.md` が `AGENTS.md` より優先される
- 合計 32 KiB(`project_doc_max_bytes = 32768`)を超えると、以降のファイルは追加されない。増やすより短くする
- `project_doc_fallback_filenames` で `CLAUDE.md` などを代わりに読ませられる
- `CODEX_HOME` を分けると用途別のグローバル指示を使い分けられる

---

設定例・手順の全文はこちらで公開しています: [Codex の AGENTS.md は既定で 32 KiB までしか読まれない:project_doc_max_bytes の設定](https://aicoding-guide.com/posts/codex-agents-md-max-bytes-fallback/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
