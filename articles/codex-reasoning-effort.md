---
title: "Codex の effort(推論の深さ)を変更する 3 つの方法:config.toml・-c フラグ・/model"
emoji: "🧭"
type: "tech"
topics: ["codex", "configtoml", "modelreasoningeffort", "reasoningeffort"]
published: false
---

Codex の応答が遅い、あるいは逆に簡単な修正なのに考えすぎている。そう感じたときに調整するのが **reasoning effort(推論の深さ)** です。Claude Code の拡張思考に相当する設定で、Codex では `model_reasoning_effort` というキーで制御します。

結論として、恒久的に変更するなら `~/.codex/config.toml` に `model_reasoning_effort = "high"` のように書き、1 回の実行だけなら `-c` フラグ、対話中なら `/model` コマンドで変更します。公式の設定リファレンスが挙げる値は `low` / `medium` / `high` / `xhigh` / `max` / `ultra` です。

> **要点**
> この記事で分かること
>
> - `model_reasoning_effort` に指定できる値と、それぞれの使いどころ
> - 恒久設定・1 回だけ・対話中・プロファイル、の 4 つの切り替え方
> - プランモードやサブエージェントにだけ別の深さを設定するキー

## まとめ

- 推論の深さは `model_reasoning_effort`。リファレンスが挙げる値は `low` / `medium` / `high` / `xhigh` / `max` / `ultra` で、使える段階はモデルとクライアントによる
- 恒久設定は `~/.codex/config.toml`、1 回だけは `-c model_reasoning_effort='"high"'`、対話中は `/model`
- 用途別に固定するなら `<名前>.config.toml` のプロファイルを作って `--profile` で選ぶ
- プランモードには `plan_mode_reasoning_effort`、サブエージェントには `agents.default_subagent_reasoning_effort`
- 深くするほど遅く高くなる。日常は中程度、難しい作業だけ上げる

---

設定例・手順の全文はこちらで公開しています: [Codex の effort(推論の深さ)を変更する 3 つの方法:config.toml・-c フラグ・/model](https://aicoding-guide.com/posts/codex-reasoning-effort/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
