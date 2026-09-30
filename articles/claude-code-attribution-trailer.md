---
title: "Claude Code のコミットから Co-Authored-By を消す:attribution.commit の設定"
emoji: "🤖"
type: "tech"
topics: ["claudecode", "git", "coauthoredby", "attribution", "settingsjson"]
published: true
---

Claude Code にコミットを作らせると、メッセージの末尾に `Co-Authored-By: Claude <noreply@anthropic.com>` のようなトレーラーが付き、PR の説明文には「Generated with Claude Code」の一文が入ります。会社のポリシーで署名を統一したい、あるいは付けたくない、という場面は珍しくありません。

結論として、settings.json の `attribution` キーで、コミットのトレーラー(`commit`)、PR の署名(`pr`)、セッションリンク(`sessionUrl`)を別々に変更・非表示にできます。

> **要点**
> この記事で分かること
>
> - `attribution` の 3 つのサブキーと、それぞれの既定
> - 全部消す設定と、独自の署名に差し替える設定
> - 非推奨の `includeCoAuthoredBy` を書いている古い設定との優先関係

## まとめ

- `attribution` の `commit`(トレーラー)、`pr`(PR 署名)、`sessionUrl`(セッションリンク)を別々に制御できる
- 全部消すなら `commit` と `pr` を空文字列、`sessionUrl` を `false`
- 差し替えるなら `commit` に任意の文字列。改行は `\n`、トレーラーは `Key: value` 形式
- `includeCoAuthoredBy` は v2.0.62 で非推奨。`attribution` を設定すると無視される
- 消す前に、プロジェクトの AI 利用申告の方針を確認する

---

設定例・手順の全文はこちらで公開しています: [Claude Code のコミットから Co-Authored-By を消す:attribution.commit の設定](https://aicoding-guide.com/posts/claude-code-attribution-trailer/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
