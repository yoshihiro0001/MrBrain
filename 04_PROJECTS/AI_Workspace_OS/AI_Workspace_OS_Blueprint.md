# AI Workspace OS Blueprint

## 位置づけ
AI Workspace OSは、ChatGPT、Codex、Cursor、NotebookLM、Google Drive、GitHub、Google Spreadsheet、MrBrainを迷わず使い分けるための運用Blueprintである。

新しいPrincipleではない。
Kernelも触らない。
AI_CONTEXTも触らない。

MrBrainは判断基準、Blueprint、Project記録の正本である。
AI Workspace OSは、その外側で「どのWorkspaceで作業するか」を決めるOperation Layerである。

目的は、AIツール同士を最小エネルギーで接続し、相談、設計、実装、保存、学習、改善、再利用の流れを止めないこと。

## 1. Workspace一覧
| Workspace | 役割 |
|---|---|
| ChatGPT / Chat | 思考整理、方針相談、違和感の言語化、構造化、判断補助 |
| Codex | MrBrain編集、ファイル作成、コード実装、ローカル確認、Git操作 |
| Cursor | 継続的なコード開発、UI実装、リファクタリング、長時間の開発作業 |
| NotebookLM | 大量資料、PDF、YouTube、マニュアル、過去資料の理解と検索 |
| GitHub | 履歴保存、復元、共有、Issue、PR、外部バックアップ |
| Google Drive | 原本保管、写真、動画、契約書、証憑、スクショ |
| Google Spreadsheet | 一時確認表、共有表、CSV確認、税理士共有、軽い見える化 |
| MrBrain | 判断基準、Blueprint、Project記録、索引、AIへ引き継ぐ正本 |

## 2. Routing Rule
| 相談内容 | 推奨Workspace |
|---|---|
| 考えを整理したい | ChatGPT / Chat |
| 本質を言語化したい | ChatGPT / Chat |
| 方針を比較したい | ChatGPT / Chat |
| MrBrainに保存したい | Codex |
| Markdownファイルを作成、修正したい | Codex |
| Git commit、push、snapshotを扱いたい | Codex |
| アプリを実装したい | Codex / Cursor |
| UIを継続的に作り込みたい | Cursor |
| コードを長時間改善したい | Cursor |
| 大量資料を理解したい | NotebookLM |
| PDF、YouTube、マニュアルを要約したい | NotebookLM |
| 情報不足を診断したい | NotebookLM / ChatGPT |
| 写真、動画、契約書、証憑を保存したい | Google Drive |
| 表で一時確認したい | Google Spreadsheet |
| 税理士や他者と確認表を共有したい | Google Spreadsheet |
| 判断基準として正本化したい | MrBrain + Codex |
| 復元地点を作りたい | Git / GitHub |

最初に決めることは、「どこで作業するか」である。
ここが決まらないと、同じ話を複数AIへ投げて循環が止まる。

## 3. Lifecycle
```md
相談
↓
Workspace Router
どこで進めるか決める
↓
設計
ChatGPT / MrBrain / Codex
↓
実装
Codex / Cursor
↓
保存
MrBrain / Google Drive / GitHub
↓
学習
NotebookLM / MrBrain
↓
改善
Operation Log / Evolution Map
↓
再利用
Blueprint / Template / Skill / Component
```

最小ルール:

```md
考える場所
↓
作る場所
↓
保存する場所
↓
学習する場所
↓
再利用する場所
```

## 4. Stop Signal
| 止まるパターン | 原因 | Workspace Routerでの解決 |
|---|---|---|
| チャットが重い | 1つの会話に詰め込みすぎ | Project別チャットへ分ける |
| どこに保存するか迷う | 原本、正本、一時表が混ざる | 原本はDrive、正本はMrBrain、履歴はGitHub |
| NotebookLMへ何を入れるか分からない | 学習用と保存用が混ざる | 大量資料だけNotebookLM、判断基準はMrBrain |
| Gitが怖い | commit、tag、復元の役割が曖昧 | 大きな編集前後だけsnapshotを作る |
| Spreadsheetが増える | Spreadsheetを正本化している | Spreadsheetは一時出力、確認表、共有表に限定する |
| Codexに何を頼むか迷う | 設計と実装が混ざる | Blueprint後にCodexへ渡す |
| CursorとCodexの違いが曖昧 | 開発場所の役割が混ざる | 単発編集はCodex、継続開発はCursor |
| 同じ説明を繰り返す | AIごとに文脈が分断される | MrBrainに正本化して参照させる |

## 5. Workspace Router責務
Workspace Routerの責務は、「相談内容を最も少ないエネルギーで目的達成できる作業場所へ振り分けること」である。

Workspace Routerは考え方そのものを持たない。
思考はKernel Routerに任せる。
対象固有情報はProjectに任せる。

責務分離:

| 層 | 役割 |
|---|---|
| Workspace Router | どこで作業するか決める |
| Kernel Router | どう考えるか決める |
| Project | 対象固有の情報を読む |
| Outcome | 何を達成するか決める |
| Delivery | 誰にどう届けるか決める |
| Artifact | 成果物形式を決める |
| Execution | 実行する |
| Learn | 結果を戻す |
| Git | 履歴と復元を担保する |

今回のBlueprintでは、Workspace Routerまでを設計対象にする。
Outcome、Delivery、Artifactは今後必要になった時に検討する。

## 6. 永続運用の抽象役割
AIツール名に依存しないため、裏側ではWorkspaceを抽象役割で扱う。

| 抽象役割 | 現在の代表 |
|---|---|
| Thinking Workspace | ChatGPT / Chat |
| Editing Workspace | Codex |
| Coding Workspace | Cursor |
| Knowledge Workspace | NotebookLM |
| Storage Workspace | Google Drive |
| History Workspace | GitHub |
| Table Workspace | Google Spreadsheet |
| Canon Workspace | MrBrain |

将来、Claude、Gemini、新しいAIが入っても、Workspace名ではなく抽象役割で差し替える。

例:

```md
ChatGPTを使う
```

ではなく、

```md
Thinking Workspaceを使う
```

と考える。

これにより、AIツールが変わっても運用ルールは変わらない。

## 7. 自己レビュー
### Layer Leak
Workspace Routerに思想や判断基準を入れるとLayer Leakになる。
Workspace Routerは作業場所の選定だけに限定する。

### 責務重複
重複しやすい組み合わせ:

| 重複しやすい場所 | 分け方 |
|---|---|
| Codex / Cursor | 単発編集はCodex、継続開発はCursor |
| MrBrain / Google Drive | 正本はMrBrain、原本はGoogle Drive |
| NotebookLM / MrBrain | 大量資料理解はNotebookLM、判断基準保存はMrBrain |
| Spreadsheet / DB | Spreadsheetは一時出力、DBは正本候補 |
| GitHub / Google Drive | GitHubは履歴、Google Driveは原本保管 |

### 概念増加
AI Workspace OSは新しいPrincipleではない。
Operation Layerとして扱う。

### Kernel肥大化
KernelにWorkspace一覧を長く入れない。
Kernelには短縮版だけを置き、詳細はこのProject Blueprintを参照する。

### Project化すべき内容
JOY、投資、NotebookLM運用、経理、Booking.com対応などはProjectに置く。
Workspace RouterにProject固有の確認項目を入れない。

### Operation Layer化すべき内容
Workspace Router、Snapshot運用、Chat分岐、保存導線はOperation Layerとして扱う。

## 8. 最小構造
AI Workspace OSの最小構造:

```md
Input
↓
Workspace Router
どこで作業するか決める
↓
Kernel Router
どう考えるか決める
↓
Project
対象固有情報を読む
↓
Execution Workspace
Codex / Cursor / NotebookLMなどで実行
↓
Storage
MrBrain / Drive / GitHubへ保存
↓
Learn
次回使える形へ戻す
```

## 9. Next Best Action
AI Workspace OSは、まずこのBlueprintをProject正本として保存する。

次の一手:
3〜5回、実際の相談でWorkspace Routerを使い、迷いが減るかを確認する。

拡張条件:
- どのWorkspaceへ行くべきか迷う場面が3回以上出た
- Codex、Cursor、NotebookLM、Drive、GitHubの使い分けで同じ迷いが繰り返された
- 成果物形式の選定が繰り返し必要になった

その時だけ、Outcome、Delivery、Artifactの責務分離を再検討する。

## 10. Future Evolution
### Capability Router（Future Candidate）
目的:
Workspaceではなく、必要能力から最適なAI、Workspace、成果物を組み立てる。

想定Flow:

```md
Goal
↓
Capability Router
↓
Workspace Router
↓
Kernel Router
↓
Project
↓
Execution
↓
Learn
↓
Git
```

現在は実績不足。

AI Workspace OSを3〜5回実運用し、必要性が確認できたら昇格を検討する。

現時点ではKernelやOperation Layerには実装しない。
