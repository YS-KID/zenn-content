---
title: "Codex CLI の config.toml でモデル・推論の深さ・プロファイルを切り替える"
emoji: "🧭"
type: "tech"
topics: ["codex", "codexcli", "configtoml"]
published: true
---

Codex CLI の挙動は `~/.codex/config.toml` で決まります。モデル、推論の深さ、承認ポリシー、サンドボックス、MCP サーバーなど、ほぼすべての設定がここに集まっています。この記事では、日常的に触ることになる項目に絞って、書き方と使い分けを整理します。

> **要点**
> この記事で分かること
>
> - `model` と `model_reasoning_effort` の指定方法と選び方
> - 用途別プロファイルの定義と `--profile` での切り替え
> - 環境変数・コマンドラインオプションとの優先順位

## まとめ

- 設定は `~/.codex/config.toml`。トップレベルに既定値、`[profiles.名前]` で用途別の設定を書く
- `model` は `/model` で確認できる名前を書き、`model_reasoning_effort` は low / medium / high / xhigh / max / ultra から選ぶ
- `codex --profile 名前` で切り替え、`profile = "名前"` で既定を決める
- 優先順位は「コマンドラインオプション > プロファイル > トップレベル > 既定」

---

設定例・手順の全文はこちらで公開しています: [Codex CLI の config.toml でモデル・推論の深さ・プロファイルを切り替える](https://aicoding-guide.com/posts/codex-config-toml/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
