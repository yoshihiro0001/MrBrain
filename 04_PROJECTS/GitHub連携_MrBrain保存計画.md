# GitHub連携 MrBrain保存計画

## 目的
MrBrainをGitHubにも保存し、Obsidian・Codex・Cursor・開発プロジェクトと連携しやすくする。

ただし、MrBrainには個人情報、税務情報、契約情報、会社情報が含まれるため、公開リポジトリにはしない。

## 現状
- MrBrainはObsidian Vaultとしてローカルに存在する。
- 現在のMrBrainフォルダは、まだGitリポジトリではない。
- `gh` CLIは `yoshihiro0001` でログイン済み。
- GitHubへ保存することは技術的に可能。
- 2026-06-29時点の確認では、`git rev-parse --is-inside-work-tree` は失敗しており、MrBrainはまだGit管理されていない。

## 基本方針
GitHubに保存する場合は、原則として非公開リポジトリにする。

目的は、GitHubへ置くこと自体ではない。

目的は、AIがMrBrainを編集しても、変更履歴が残り、失敗時に戻せて、拡張しても壊れにくい状態を作ることである。

推奨リポジトリ名:
```md
MrBrain
```

推奨形:
```md
GitHub private repository
└── MrBrain Vault
    ├── 00_HOME
    ├── 01_ME
    ├── 02_LIFE
    ├── 03_BUSINESS
    ├── 04_PROJECTS
    ├── 05_IDEAS
    ├── 06_KNOWLEDGE
    ├── 07_SYSTEM
    ├── 99_ARCHIVE
    └── AGENTS.md
```

## GitHubに入れてよいもの
- Markdownの索引
- 目的、判断、ルール、設計思想
- 原本の保管場所
- AIへの指示
- プロジェクト計画
- 安全に要約した会社情報

## GitHubに入れないもの
- パスワード
- APIキー
- 秘密鍵
- マイナンバー
- 銀行暗証番号
- クレジットカード番号全文
- 契約書原本
- 申告書原本
- 給与明細原本
- レシート画像原本
- Google Driveの認証情報

## 理想の役割分担
| 役割 | 使うもの | 持たせる内容 |
|---|---|---|
| 履歴管理 | Git / GitHub private | MrBrainのMarkdown、設計、ルール、Blueprint、索引 |
| 原本保管 | Google Drive | 写真、動画、契約書、証憑、スクショ、申告書、給与資料などの原本 |
| 思考OS | MrBrain | 判断基準、索引、要約、設計、リンク、AI指示 |
| 大量資料の理解 | NotebookLM | PDF、動画文字起こし、長文資料、複数資料の検索と理解 |
| 編集・整理・実装 | Codex | Markdown整理、構造監査、設計書作成、コード実装、Git操作補助 |

## 原本と索引のルール
```md
原本はGitに入れない。
MrBrainには原本の場所、要約、確認日、AIに渡してよい範囲だけを書く。
MarkdownはGitで履歴管理する。
AI編集前はcommitする。
大きな変更後もcommitする。
```

原本の例:
- 契約書PDF
- 申告書、決算書、給与明細
- レシート画像、請求書画像
- ホテル信号調査の写真、動画、スクショ
- Google Driveや外部サービスの認証情報

MrBrainに置くもの:
- 原本の保管場所
- 何の資料かの要約
- 関連Projectや判断基準へのリンク
- 次に確認すること
- AIへ渡してよい範囲

## 注意が必要なファイル
以下は、GitHubに入れる前に内容確認する。

- `01_ME`
- `02_LIFE`
- `03_BUSINESS`
- `04_PROJECTS/スプレッドシート整理`
- `07_SYSTEM/AI_CONTEXT.md`
- `07_SYSTEM/DECISION_LOG.md`

## .gitignore方針
Obsidianの作業状態、不要な一時ファイル、秘密情報を除外する。

```gitignore
.DS_Store
.obsidian/workspace.json
.obsidian/workspace-mobile.json
.trash/
*.tmp
*.log
.env
.env.*
*.key
*.pem
*.p12
*.pfx
*.jpg
*.jpeg
*.png
*.heic
*.mov
*.mp4
*.pdf
*.xlsx
*.xls
*.docx
```

## 保存・復元・拡張ルール設計案

### 1. まずやること
いきなりGit初期化やpushをしない。

最初にやるのは、Git管理状態の監査である。

確認すること:
- MrBrainがGit管理されているか
- `.gitignore` が必要か
- Gitに入れるべきMarkdownと、入れてはいけない原本が混ざっていないか
- 写真、動画、契約書、証憑、スクショ、Excel、PDFがVault内にないか
- private GitHubへ保存する範囲はどこまでか

### 2. Git管理前の安全確認
Git管理する前に、次を確認する。

```md
Gitに入れる:
- Markdown
- README
- AGENTS.md
- 設計、索引、要約、判断基準

Gitに入れない:
- 原本ファイル
- 証憑画像
- 契約書PDF
- 申告書PDF
- 給与資料
- 個人情報の全文
- 認証情報
```

### 3. AI編集前後の運用
AIがMrBrainを編集する前後は、次の順番にする。

```md
編集前:
1. 現在の変更状態を確認する
2. 未保存の重要変更があればcommitする
3. 変更予定ファイルを確認する

編集後:
1. 変更ファイル一覧を見る
2. 変更内容を要約する
3. 個人情報や原本が混入していないか確認する
4. 問題なければcommitする
```

### 4. 失敗した時の戻し方
Git管理後は、次の戻し方を基本にする。

```md
小さなミス:
- 変更内容を確認して、該当ファイルだけ戻す

大きなミス:
- 直前のcommitへ戻す

判断に迷う場合:
- すぐ戻さず、差分を確認してから決める
```

注意:
AIは勝手に破壊的な戻し方をしない。
`git reset --hard` や一括削除は、ユーザー確認後だけ行う。

### 5. 拡張時のルール
MrBrainを拡張する時は、次を守る。

- 新規ファイルは、既存ファイルへ統合できないか先に確認する
- 原本は入れず、索引と要約にする
- Project具体例を`01_ME`やKernelへ上げない
- 大きな構造変更は、変更前にcommitする
- 大きな構造変更後もcommitする
- Layer Integrity Checkで置き場所を確認する

## Git導入ロードマップ
1. Git管理状態を監査する。
2. `.gitignore` を作る前に、除外対象を確定する。
3. Vault内に原本ファイルがないか確認する。
4. `.gitignore` を作る。
5. `git init` する。
6. `git status` で入るファイルを確認する。
7. 秘密情報・税務情報・契約情報の混入を確認する。
8. 初回commitする。
9. GitHubにprivateリポジトリを作る。
10. 初回pushする。

## 実行前に確認すること
GitHubへ実際にpushする前に、次を確認する。

```md
リポジトリ名:
公開範囲: private
GitHubに保存してよい範囲:
除外したいファイル:
```

## 判断
MrBrainをGitHubに保存するのは有効。

理由:
- CodexやCursorから扱いやすくなる
- 履歴が残る
- 間違えて消しても戻せる
- AGENTS.mdを入口にできる
- ObsidianをAIの永続メモリーとして運用しやすい

ただし、必ず非公開リポジトリにする。

## 不安を減らすための設計書提案
次に作るべき設計書は、新規思想ではなく運用設計である。

候補名:
```md
MrBrain 保存・復元・拡張ルール
```

置き場所:
```md
07_SYSTEM
```

理由:
- Git、Drive、MrBrain、NotebookLM、Codexの役割分担は、Projectを超えて毎回使う運用ルールだから
- AIが編集前に参照する安全ルールとして使えるから

ただし、現時点では新規作成せず、この計画ファイルで設計を固める。
内容が安定したら、`07_SYSTEM`へ正本化する。

設計書に入れるべき章:
1. 目的
2. 役割分担
3. Gitに入れるもの / 入れないもの
4. 原本と索引のルール
5. AI編集前の確認
6. AI編集後の確認
7. commitルール
8. GitHub private運用
9. 失敗時の戻し方
10. 拡張時のLayer Integrity Check
