---
title: "Gemini CLI v0.62 の変更点:gemini-3.8-flash と gemini-3.5-flash-lite が追加"
emoji: "♊"
type: "tech"
topics: ["geminicli", "settingsjson", "oauth"]
published: true
---

Gemini CLI の v0.62.0 は、修正が大半を占めるなかに **モデルの追加が 1 件** 含まれるリリースです。

結論として、注目すべきは `gemini-3.8-flash` と `gemini-3.5-flash-lite` の追加です。あわせて、OAuth のリフレッシュトークンを保持する修正と、Windows のシェル実行まわりの修正が入っています。

なお v0.62.0 のリリースノートは **PR のタイトルが並んだ一覧** で、各変更の説明文は付いていません。この記事では PR と公式の設定リファレンスで裏を取れた範囲だけを書き、取れなかったものはその旨を明記します。

> **要点**
> この記事で分かること
>
> - 追加された 2 つのモデル ID と、どの層の最新版なのか
> - `settings.json` の `model.name` でモデルを指定する書き方
> - OAuth・Windows・プロキシに入った修正

## まとめ

- v0.62.0 の目玉は `gemini-3.8-flash` と `gemini-3.5-flash-lite` の追加。どちらも公式設定リファレンスで確認できる
- 既存の `gemini-3.5-flash` と `gemini-3.1-flash-lite` は base 層へ移り、新しい 2 つが最新版になる
- モデルは `settings.json` の `model.name` で指定する。ユーザー設定は `~/.gemini/settings.json`
- OAuth のリフレッシュトークンを保持する修正が入った。ログインが切れる症状があるなら上げる価値がある
- 新モデルが選択肢に出ない場合は段階的な公開が理由の可能性があるが、その仕組みは公式ドキュメントでは確認できなかった

---

設定例・手順の全文はこちらで公開しています: [Gemini CLI v0.62 の変更点:gemini-3.8-flash と gemini-3.5-flash-lite が追加](https://aicoding-guide.com/posts/gemini-cli-update-0-62/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
