# MrBrain 保存・復元・拡張ルール

## 目的
AIがMrBrainを編集しても、いつでも安全に戻せる状態を作る。

このファイルは、新しい思想ではなく、GitとGitHubを使った保存・復元・拡張の実運用ルールである。

## 役割分担
| 使うもの | 役割 |
|---|---|
| Git | ローカルの変更履歴を残す |
| GitHub private | MrBrainのMarkdownを外部にも保存する |
| MrBrain | 判断基準、索引、要約、設計、AI指示を保存する |
| Google Drive | 写真、動画、契約書、証憑、スクショ、申告書などの原本を保管する |
| Codex | 編集、整理、実装、Git操作補助を行う |

## commitとは何か
commitは、その時点のMrBrainを保存する記録である。

使い方:
- 小さな編集の区切りを保存する
- AI編集前後の差分を残す
- 後から「何を変えたか」を確認する

例:
```bash
git status --short
git add .
git commit -m "Update MrBrain notes"
```

## tag / snapshotとは何か
tagは、特定のcommitに分かりやすい名前を付ける仕組みである。

MrBrainでは、重要な復元地点をsnapshotとして扱う。

commit hashだけでは分かりにくいので、次のような名前を付ける。

```md
snapshot-20260629-mrbrain-github-initial-sync
```

## tag名の命名ルール
### 安定地点
```md
snapshot-YYYYMMDD-内容
```

例:
```md
snapshot-20260629-mrbrain-github-initial-sync
```

### 大きな作業前
```md
before-YYYYMMDD-作業名
```

例:
```md
before-20260629-kernel-router-restructure
```

### 大きな作業後
```md
after-YYYYMMDD-作業名
```

例:
```md
after-20260629-kernel-router-restructure
```

## いつsnapshotを作るか
snapshotは、毎回作るものではない。

次の場合に作る。

- GitHub初回同期が完了した時
- 大きな構造変更の前
- 大きな構造変更の後
- Kernel Router、AGENTS、AI_CONTEXTなど入口ファイルを大きく変える前後
- しばらく安定運用できた時
- 「ここには戻れるようにしたい」と感じた時

## 現在の最初のsnapshot
```md
snapshot-20260629-mrbrain-github-initial-sync
```

意味:
- MrBrainをGit管理し、GitHub `yoshihiro0001/MrBrain` の `main` に初回同期できた地点。

## AI編集前の確認
AIが大きく編集する前に確認する。

```bash
git status --short
git log --oneline -5
git tag --list
```

未commitの変更がある場合は、先に内容を確認する。

## AI編集後の確認
編集後は、次を確認する。

```bash
git status --short
git diff
```

問題なければcommitする。

```bash
git add .
git commit -m "変更内容"
git push
```

## snapshotを作る方法
```bash
git tag -a snapshot-YYYYMMDD-内容 -m "Snapshot: 内容"
git push origin snapshot-YYYYMMDD-内容
```

大きな作業前:
```bash
git tag -a before-YYYYMMDD-作業名 -m "Before: 作業名"
git push origin before-YYYYMMDD-作業名
```

大きな作業後:
```bash
git tag -a after-YYYYMMDD-作業名 -m "After: 作業名"
git push origin after-YYYYMMDD-作業名
```

## 戻したい時の基本手順
いきなり戻さない。

まず確認する。

```bash
git status --short
git log --oneline -5
git tag --list
```

戻したいsnapshotの中身を見る。

```bash
git show snapshot-20260629-mrbrain-github-initial-sync
```

## 1ファイルだけ戻す方法
1ファイルだけ戻す場合は、全体を戻さない。

```bash
git restore --source snapshot-20260629-mrbrain-github-initial-sync "対象ファイル.md"
```

戻した後に確認する。

```bash
git diff
```

問題なければcommitする。

## 全体を戻す方法
全体を戻す操作は危険である。

まず、戻したい地点を確認する。

```bash
git tag --list
git log --oneline --decorate -10
```

戻す候補:
```bash
snapshot-20260629-mrbrain-github-initial-sync
```

実際に全体を戻すコマンド:
```bash
git reset --hard snapshot-20260629-mrbrain-github-initial-sync
```

## reset --hard の注意
`git reset --hard` は危険である。

理由:
- 未commitの変更が消える
- AIやユーザーが直前に書いた内容も消える
- 間違えると必要な変更を失う

ルール:
- AIは勝手に実行しない
- ユーザーが明確に許可した時だけ実行する
- 実行前に `git status --short` と `git diff` を必ず確認する

## 原本ファイルの扱い
Gitには原本を入れない。

Gitに入れないもの:
- 写真
- 動画
- 契約書
- 証憑
- スクショ
- 申告書
- 給与資料
- APIキー
- パスワード

MrBrainには、原本の場所と要約だけを書く。

## 運用ルール
- 小さな編集はcommitで保存する
- 大きな編集前後はsnapshotを作る
- AI編集前は `git status --short` を見る
- AI編集後は `git diff` を見る
- GitHubへpushして、ローカルだけに閉じない
- 復元時は、まず1ファイル復元を優先する
- 全体復元は最後の手段にする
