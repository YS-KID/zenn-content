---
title: "Claude Code の WebFetch を特定ドメインだけ許可する設定"
emoji: "🤖"
type: "tech"
topics: ["claudecode", "webfetch", "permissions"]
published: true
---

Claude に調べ物をさせたいが、任意のサイトへ自由にアクセスさせたくない。この要求は `permissions` の `WebFetch(domain:...)` ルールで表現できます。

ルールはリクエスト先の**ホスト名**に対して照合されます。大文字小文字は区別されず、末尾のドットは無視されるため、`example.com.` と `example.com` は同じ扱いです。

> **要点**
> この記事で分かること
>
> - `WebFetch(domain:...)` の書き方とワイルドカードの範囲
> - `WebFetch` と `WebFetch(domain:*)` の違い
> - サンドボックスの通信許可とリダイレクトの注意点

## まとめ

- `WebFetch(domain:...)` はホスト名に照合され、大文字小文字と末尾のドットを区別しない
- `*.example.com` はサブドメインだけに一致し、`example.com` 自体は別に書く
- 末尾ワイルドカードはドットを越えないため、`example.*` は `example.evil.com` に一致しない
- 全許可には bare の `WebFetch` と `WebFetch(domain:*)` があり、後者だけがサンドボックスの到達範囲も広げる
- 別ホストへのリダイレクト先は、改めて許可か承認が必要になる

---

設定例・手順の全文はこちらで公開しています: [Claude Code の WebFetch を特定ドメインだけ許可する設定](https://aicoding-guide.com/posts/claude-code-webfetch-domain-allow/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
