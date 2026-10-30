---
title: "Codex CLI v0.165 で Vertex AI が組み込みプロバイダになりメモリが既定で有効になった"
emoji: "🧭"
type: "tech"
topics: ["codex", "codexcli", "vertexai"]
published: true
---

Codex CLI の v0.165.0 は、新機能 6 件と修正 6 件のリリースです。設定に関わるのは **Vertex AI プロバイダの追加** と **メモリの既定有効化** の 2 つです。

どちらも、リリースノートの記述が公式の設定リファレンスにまだ反映されていません。導入する前に、手元の挙動を確認することをおすすめします。

> **要点**
> この記事で分かること
>
> - `model_provider = "gcp"` で使える Vertex AI プロバイダが追加されたこと
> - メモリの既定値について、リリースノートと設定リファレンスが食い違っていること
> - 会話の途中で推論の深さを変えられるようになったこと

## まとめ

- `model_provider = "gcp"` で使える Vertex AI プロバイダが組み込みになった
- ただし `gcp` は公式の設定リファレンスでは確認できなかった。組み込み ID は `openai` / `ollama` / `lmstudio` のまま
- `model_provider` はプロジェクトローカルの `.codex/config.toml` では無視される。ユーザーレベルに書く
- メモリが新規プロファイルで既定有効になったとされるが、設定リファレンスは `off by default` のまま
- マーケットプレイスの URL 検証の抜けが塞がれた

---

設定例・手順の全文はこちらで公開しています: [Codex CLI v0.165 で Vertex AI が組み込みプロバイダになりメモリが既定で有効になった](https://aicoding-guide.com/posts/codex-update-0-165/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
