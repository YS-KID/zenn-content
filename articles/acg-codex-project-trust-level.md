---
title: "Codex の「このフォルダを信頼しますか」を消す:trust_level = 'trusted' の書き方"
emoji: "🧭"
type: "tech"
topics: ["codex", "configtoml", "trustlevel"]
published: false
---

clone したばかりのリポジトリで `codex` を起動すると、そのフォルダを信頼するかどうかを聞かれます。この答えは `~/.codex/config.toml` に記録され、プロジェクト内の `.codex/` 配下の設定を読むかどうかを左右します。

結論として、信頼状態は `[projects."<絶対パス>"]` の `trust_level` で管理されており、`untrusted` のプロジェクトでは `.codex/config.toml`、プロジェクトの hooks、rules が **すべて無視されます**。

> **要点**
> この記事で分かること
>
> - `trust_level` の書き方と 2 つの値
> - untrusted のときに読み込まれない設定の範囲
> - プロジェクト設定が設定レイヤーのどこに位置するか

## まとめ

- 信頼状態は `~/.codex/config.toml` の `[projects."<絶対パス>"] trust_level` に記録される。値は `trusted` / `untrusted`
- untrusted では `.codex/config.toml`、プロジェクトの hooks、rules がすべて無視される
- 信頼した瞬間にそれらが有効になるので、初めてのリポジトリは `.codex/` を見てから答える
- 信頼済みのプロジェクト設定は、プロファイルやユーザー設定より優先される
- worktree は別パスとして扱われる

---

設定例・手順の全文はこちらで公開しています: [Codex の「このフォルダを信頼しますか」を消す:trust_level = "trusted" の書き方](https://aicoding-guide.com/posts/codex-project-trust-level/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
