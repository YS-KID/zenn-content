---
title: "Gemini CLI v0.68 で rootless Podman のサンドボックスとパス境界の判定が直った"
emoji: "♊"
type: "tech"
topics: ["geminicli", "podman", "hooks"]
published: true
---

Gemini CLI の v0.68.0 は、リリースノートに **まとめの文章が無く** PR の一覧だけが並ぶ回です。新機能は 1 件で、残りは修正です。

地味に見えますが、**境界の判定に関わる修正が 3 件まとまっている**のがこのリリースの性格です。どれも「公式ドキュメントが書いていた挙動が、実際には一部の環境で成立していなかった」種類のものです。

> **要点**
> この記事で分かること
>
> - rootless Podman で `--userns=keep-id` が渡る条件と、上書きの方法
> - Windows でのルート判定とシンボリックリンクの解決に入った修正
> - 追加された拡張の検証コマンドとフックの `SubagentStop` が、まだ公式ドキュメントに無いこと

## まとめ

- v0.68.0 はリリースノートにまとめの文章が無く、新機能 1 件・修正 28 件の構成
- rootless Podman では `--userns=keep-id` が渡る。これはドキュメント化された挙動で、別のモードにするなら `SANDBOX_FLAGS` に `--userns` を自分で足す
- Windows のルート判定と GlobTool のシンボリックリンク解決が直った。ただしどちらも仕様としての記述は公式ドキュメントに無い
- 追加された拡張の検証コマンドと、フックの `SubagentStop` は、いずれも公式ドキュメントに記載がない

---

設定例・手順の全文はこちらで公開しています: [Gemini CLI v0.68 で rootless Podman のサンドボックスとパス境界の判定が直った](https://aicoding-guide.com/posts/gemini-cli-update-0-68/)

※ この記事は要約版です。仕様変更に合わせた更新は上記ページで行います。
