---
title: "Codex の workspace-write で作業ディレクトリ外にも書き込ませる writable_roots と /tmp の扱い"
emoji: "🧭"
type: "tech"
topics: ["codex", "writableroots", "workspacewrite", "configtoml"]
published: false
---

Codex を `workspace-write` で動かしていると、`~/.cache` や `~/.pyenv` のような作業ディレクトリ外への書き込みでビルドやパッケージのインストールが失敗することがあります。サンドボックスが書き込み先を制限しているためです。

結論として、書き込みを許可する場所は `[sandbox_workspace_write]` の `writable_roots` に追加できます。逆に、既定で書き込める `/tmp` と `$TMPDIR` を外すのが `exclude_slash_tmp` と `exclude_tmpdir_env_var` です。

> **要点**
> この記事で分かること
>
> - `workspace-write` で既定で書き込める場所
> - `writable_roots` の書き方と、`/tmp` / `$TMPDIR` の除外設定
> - `.git/` や `.codex/` が書けない理由と、フル権限との違い

## まとめ

- `workspace-write` の既定で書けるのは作業ディレクトリと `/tmp`、`$TMPDIR`
- 作業ディレクトリ外は `[sandbox_workspace_write] writable_roots` に絶対パスで追加する。ホーム全体は足さない
- `/tmp` と `$TMPDIR` を外すのは `exclude_slash_tmp` / `exclude_tmpdir_env_var`(既定 `false`)
- `.git/` と `.codex/` は環境によっては読み取り専用のまま
- ネットワークは `network_access` で別に制御する

---

設定例・手順の全文はこちらで公開しています: [Codex の workspace-write で作業ディレクトリ外にも書き込ませる writable_roots と /tmp の扱い](https://aicoding-guide.com/posts/codex-writable-roots/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
