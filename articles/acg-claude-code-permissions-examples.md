---
title: "Claude Code の permissions 設定例、npm scripts は自動・git push は確認・force push "
emoji: "🤖"
type: "tech"
topics: ["claudecode", "permissions", "allow", "ask", "deny"]
published: true
---

Claude Code に開発を任せるとき、多くの人が欲しいのは次の 3 つの線引きです。`npm run lint` や `npm run test` のような自分で書いた scripts は確認なしで走らせたい。`git push` はリモートに影響するので、直前に一度だけ自分で確認したい。`git push --force` は何があっても実行させたくない。

この 3 つは、`settings.json` の `permissions` を allow・ask・deny の 3 層で書けば 1 つの設定で実現できます。この記事では完成形を先に示し、各層の書き方と落とし穴を順に説明します。

> **要点**
> この記事で分かること
>
> - allow・ask・deny を組み合わせた settings.json の完成形
> - `:*` の前方一致の意味と、install 系を巻き込まない書き方
> - ask が allow より強い理由と、「今後も許可」を選んでも確認が続く仕組み
> - force push の表記ゆれ(`-f`、`--force-with-lease`、オプション順)を deny で押さえる方法

## まとめ

- allow・ask・deny は deny → ask → allow の順に評価され、先に一致したものが結果を決める
- `Bash(npm run:*)` で scripts をまとめて許可できる。`npm install` は別の先頭文字列なので巻き込まれない。pnpm や npx を全体許可するなら install 系を ask に置く
- `Bash(git push:*)` を ask に書くと push の直前に必ず確認が入り、「今後も許可」を選んでも ask が残る限り続く
- force push は `--force`、`-f`、`--force-with-lease`、オプション順違いを deny に列挙する。deny はどのモードでも効き、個人設定で解除できない
- deny は保険なので、守りたいブランチはリモートのブランチ保護も併用する

---

設定例・手順の全文はこちらで公開しています: [Claude Code の permissions 設定例、npm scripts は自動・git push は確認・force push は禁止にする](https://aicoding-guide.com/posts/claude-code-permissions-examples/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
