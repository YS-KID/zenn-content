---
title: "Codex の推論(reasoning)の表示を消す・詳しくする設定:hide_agent_reasoning と要約の粒度"
emoji: "🧭"
type: "tech"
topics: ["codex", "configtoml", "hideagentreasoning", "reasoning"]
published: false
---

Codex は応答の途中で「何を考えているか」の要約を表示します。作業の追跡には便利ですが、ログを流し読みしたいときや、`codex exec` の出力をスクリプトで扱いたいときには邪魔になります。逆に、なぜその判断をしたのかをもっと詳しく見たい場面もあります。

結論として、表示は `hide_agent_reasoning`(消す)と `show_raw_agent_reasoning`(生の推論を出す)、要約の粒度は `model_reasoning_summary` で制御します。推論の **深さ** を決める `model_reasoning_effort` とは別の設定です。

> **要点**
> この記事で分かること
>
> - 表示に関する 3 つのキーの役割と既定
> - 「表示」の設定と「深さ」の設定(`model_reasoning_effort`)の違い
> - モデルやプロバイダによって効かないケース

## まとめ

- 表示を消すのは `hide_agent_reasoning = true`、生の推論を出すのは `show_raw_agent_reasoning = true`
- 要約の粒度は `model_reasoning_summary`(`auto` / `concise` / `detailed` / `none`)
- 推論の深さは別のキー `model_reasoning_effort`。表示を消しても推論とトークン消費は続く
- `codex exec` 用のプロファイルで非表示にすると出力が安定する
- 生の推論はモデル・プロバイダが対応していないと表示されない

---

設定例・手順の全文はこちらで公開しています: [Codex の推論(reasoning)の表示を消す・詳しくする設定:hide_agent_reasoning と要約の粒度](https://aicoding-guide.com/posts/codex-hide-agent-reasoning/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
