# MrBrain GitHub Obsidian Codex連携計画

## 目的
MrBrainを、Obsidianで使いやすく、GitHubに保存でき、Codexと連携しやすい状態にする。

## 現在の状態
- MrBrainはObsidian Vaultとして作成済み。
- `AGENTS.md` があり、AIが作業前に読む入口がある。
- 5スプレッドシートのAI引き継ぎがある。
- 会社マスター索引がある。
- GitHub CLIはログイン済み。
- MrBrain自体はまだGitリポジトリではない。

## 解決したい課題
1. Obsidianで便利に使いこなしたい。
2. Codexが毎回同じ説明なしで動けるようにしたい。
3. GitHubにも安全に保存したい。
4. 個人情報・税務情報・契約情報を守りたい。
5. 開発とMrBrainをつなげたい。

## 推奨構造
```md
Obsidian
↓
MrBrain Vault
↓
AGENTS.md
↓
Codex
↓
GitHub private repository
↓
Cursor / アプリ開発
```

## 最初の完成条件
- `AGENTS.md` が作業入口になる
- `AI_CONTEXT.md` が短い背景情報になる
- `PROJECTS.md` がプロジェクト入口になる
- `SPREADSHEET_INDEX.md` がスプレッドシート入口になる
- `会社マスター索引.md` が会社情報入口になる
- GitHubへprivateで保存できる状態になる

## GitHub保存の前にやること
1. `.gitignore` を整える
2. Gitリポジトリ化する
3. `git status` で対象ファイルを見る
4. 秘密情報チェックをする
5. private GitHubリポジトリを作る
6. 初回pushする

## 注意
GitHubに保存する場合、必ずprivateにする。

MrBrainは公開用ではない。
自分専用の第二の脳であり、個人・会社・税務・契約の索引を含む。

## 今すぐできること
- MrBrainをObsidianで開いて使う
- Codexには `AGENTS.md` を入口にさせる
- 新しい発見は適切な場所へ保存する
- GitHub保存前の安全チェックを行う

## まだ確認が必要なこと
```md
GitHubリポジトリ名:
公開範囲: privateでよいか
GitHubに入れたくないフォルダ:
Obsidian設定を含めるか:
```
