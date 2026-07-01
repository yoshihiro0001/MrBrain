# AI Workspace OS Blueprint

## 位置づけ
AI Workspace OSは、ChatGPT、Codex、Cursor、NotebookLM、Google Drive、GitHub、Google Spreadsheet、MrBrainを迷わず使い分けるための運用Blueprintである。

新しいPrincipleではない。
Kernelも触らない。
AI_CONTEXTも触らない。

MrBrainは判断基準、Blueprint、Project記録の正本である。
AI Workspace OSは、その外側で「どのWorkspaceで作業するか」を決めるOperation Layerである。

目的は、AIツール同士を最小エネルギーで接続し、相談、設計、実装、保存、学習、改善、再利用の流れを止めないこと。

## AI Tool Operation Map
各ツールの現実的な役割を整理する。

| Tool | 現実運用での役割 |
|---|---|
| ChatGPT | 思考整理、違和感の言語化、設計レビュー、Codexへの指示文作成 |
| Codex | MrBrainのMarkdown編集、ファイル作成、Git commit / push、コード実装の小〜中タスク |
| Cursor | アプリ本体の継続開発、UI実装、コードリファクタリング、長時間の開発作業 |
| NotebookLM | PDF、YouTube、マニュアル、外部資料、大量ドキュメントの理解、要約、質問 |
| GitHub | 履歴保存、復元、snapshot、外部バックアップ |
| Google Drive | 原本保管、写真、動画、証憑、契約書、スクショ |
| MrBrain | 判断基準、Blueprint、Project正本、AIへの引き継ぎ情報 |
| Spreadsheet | 一時確認表、共有表、CSV確認、税理士共有 |

## Daily Operation Flow
基本の流れ:

```md
1. ChatGPTで考える
2. Codexへの指示文を作る
3. CodexがMrBrainを編集する
4. GitHubへcommit / pushする
5. 必要ならNotebookLM用パッケージを作る
6. MrBrain / Evolution Map / TASKSへ戻す
```

## 迷った時の判定
- 考えるだけなら ChatGPT
- ファイルを変えるなら Codex
- アプリを作り込むなら Cursor
- 大量資料を読むなら NotebookLM
- 原本を置くなら Google Drive
- 正本を書くなら MrBrain
- 履歴を残すなら GitHub

## 注意
- ChatGPTの長い会話は正本にしない
- 重要な判断はMrBrainへ戻す
- Codexの長い会話も正本にしない
- 最終的な成果物、決定、BlueprintだけMrBrainへ保存する
- NotebookLMは知識理解用であり、正本ではない
- GitHubは履歴であり、思考の正本ではない

## Operation Map自己レビュー
Workspace Routerとの重複:
この節はWorkspace Routerの詳細運用であり、Kernelへ入れる短縮ルールではない。

Kernel:
毎回読むには長いため、Kernelへ入れない。

AI_CONTEXT:
現在地ではなく運用Mapなので、AI_CONTEXTへ入れない。

将来の差し替え:
ツール名は現実運用のために書くが、裏側ではThinking Workspace、Editing Workspace、Knowledge Workspaceなどの抽象役割で差し替え可能にする。

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
Future Candidateは、思いつきではなく研究テーマとして管理する。

この運用は新しいPrincipleではない。
MrBrainのEvolution運用ルールとして扱う。

### Future Candidate Template
| 項目 | 内容 |
|---|---|
| Status | `Future Candidate` / `Validating` / `Principle Candidate` / `Adopted` / `Rejected` |
| Evidence | 現在いくつの分野で成立したか |
| Confidence | 現在どれくらい確信しているか |
| Promotion Rule | 何を満たしたら昇格するか |

育て方:

```md
思いつき
↓
Evidence収集
↓
Confidence更新
↓
Promotion Rule達成
↓
Principle Candidate
↓
Adopted
```

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

### Universal Event Model（Future Candidate）
目的:
Root Structureを見つけた後、対象を最小構造へ分解する共通モデルになり得るかを検証する。

Status:
Future Candidate

Evidence:

| 分野 | 状態 |
|---|---|
| Hotel | ✅ |
| AI Workspace | ✅ |
| Investment | ⬜ |
| Human Body | ⬜ |
| Accounting | ⬜ |
| Mail | ⬜ |
| Human Communication | ⬜ |

Confidence:
40%

Promotion Rule:
5分野以上で成立した場合のみ、Principle Candidateへの昇格を検討する。

現在の仮説:

```md
Input
↓
Event
↓
Rule
↓
State
↓
Output(UI)
```

説明:

| 要素 | 意味 |
|---|---|
| Input | 最初に世界へ入ってくる入力、刺激、信号 |
| Event | 実際に発生した出来事 |
| Rule | その出来事をどう解釈、計算、変換するか |
| State | 現在の状態、属性、履歴 |
| Output | 人間が見る画面、結果、通知、行動 |

現在確認できている例:

```md
ホテル
↓
Input: 電気信号
↓
Event: 入室、退室、延長
↓
Rule: 料金計算
↓
State: 利用中、清掃中
↓
Output: ホテル画面、売上
```

今後検証する対象:

- [ ] 投資
- [ ] 人体
- [ ] 経理
- [ ] 契約
- [ ] メール対応
- [ ] 人間関係
- [ ] AI Workspace OS
- [ ] AIの思考プロセス

検証観点:
AIが問題を解釈し、回答を生成する過程も、Universal Event Modelで説明できるかを検証する。

```md
Input
↓
Event
↓
Rule
↓
State
↓
Output(UI)
```

確認したい対象:

- [ ] ChatGPT
- [ ] Codex
- [ ] Cursor
- [ ] NotebookLM
- [ ] 将来追加されるAI

これらの内部処理や運用フローも、Universal Event Modelで共通に説明できるかを確認する。

もし3〜5種類以上のAI・ツールでも成立するなら、Universal Event Modelは「人間の思考」ではなく、「AIを含めた情報処理の共通構造」である可能性がある。

現時点ではFuture Candidateとして保存する。
Kernel、Principle、AI_CONTEXTには反映しない。

### Processing Engine Hypothesis（Future Candidate）
目的:
Universal Event Model内の`Rule`は、静的なルールではなく、状態を変換するProcessing Engineとして表現した方が自然ではないかを検証する。

Status:
Future Candidate

Evidence:

| 分野 | 状態 |
|---|---|
| Investment | ✅ 条件付き |
| Hotel | ⬜ |
| Human Body | ⬜ |
| AI | ⬜ |
| Accounting | ⬜ |

Confidence:
25%

現在の仮説:

```md
Input
↓
Event
↓
Processing Engine
↓
State
↓
Output
```

説明:
投資検証では、`Rule`を「固定された判断ルール」と見るより、Eventを価値、財務状態、市場評価へ変換する処理エンジンとして見た方が自然だった。

例:

```md
JDI
↓
Input: 資金調達、工場売却、技術開発、受注
↓
Event: 契約、量産、構造改革、IR発表
↓
Processing Engine: 固定費構造、資金繰り、希薄化、商業化、損益分岐点
↓
State: 赤字、負の純資産、構造改革中、量産前
↓
Output: 売上、利益、株価、時価総額、市場評価
```

検証対象:

- [ ] ホテル
- [ ] 人体
- [ ] AI
- [ ] 経理

Promotion Rule:
ホテル、人体、AI、経理を含む3〜5分野でProcessing Engineの方が一貫して自然なら、Universal Event Modelの改訂候補としてレビューする。

注意:
現時点ではUniversal Event Model自体は修正しない。
Kernel、Principle、AI_CONTEXTには反映しない。

### Goal-to-System Blueprint（Future Candidate）
目的:
ユーザーのGoalから、必要なCapability、Human Agent、AI Agent、Workspace、Artifact、Execution、Approval、Learning Loopまでを一気通貫で設計するための共通Blueprint候補。

Status:
Future Candidate

Evidence:

| 分野 | 状態 |
|---|---|
| HOTEL JOY | ⬜ |
| メルカリ出品 | ✅ 仮説例 |
| Booking返信 | ⬜ |
| 経理 | ⬜ |
| 投資 | ⬜ |
| 人体ログ | ⬜ |
| AI Workspace OS | ⬜ |

Confidence:
30%

現在の仮説:
どんなGoalでも、以下の順番で分解すると、抜け漏れなくシステム化できる可能性がある。

```md
Goal
↓
Outcome
↓
Capability Map
↓
Agent Role Map
↓
Workspace Map
↓
Artifact Map
↓
Execution Plan
↓
Approval Flow
↓
Learning Loop
```

説明:

| 要素 | 意味 |
|---|---|
| Goal | 何を達成したいか |
| Outcome | 何が変われば成功か |
| Capability Map | 必要な能力 |
| Agent Role Map | Human Agent / AI Agent / Automation Agent の役割分担 |
| Workspace Map | ChatGPT / Codex / Cursor / NotebookLM / Git / Drive / DB / Browser Automationなど、どこで実行するか |
| Artifact Map | 生成すべき成果物 |
| Execution Plan | 実行順序 |
| Approval Flow | どこで人間承認を挟むか |
| Learning Loop | 実行結果をどう保存、改善するか |

Browser Automationの位置づけ:
ブラウザ自動操作はExecution Componentの一つである。

最初から完全自動化に行かない。

```md
Human承認付き
↓
半自動
↓
APIがあればAPI
↓
ブラウザ自動操作
↓
完全自動
```

メルカリ例:

```md
Goal:
商品を売り切る

Capability:
- 相場調査
- 価格設定
- 文章生成
- 写真整理
- 出品
- コメント返信
- 在庫管理
- 値下げ
- 発送管理

Human Agent:
- 写真撮影
- 商品状態確認
- 最終承認
- 発送

AI Agent:
- 相場調査
- 説明文作成
- 価格提案
- 返信案
- 値下げ提案

Automation Agent:
- 出品下書き作成
- 在庫表更新
- 通知
- 可能ならブラウザ入力補助

Approval:
- 出品前
- 価格変更前
- 返信前
- 発送前

Learning:
- 売れた価格
- 閲覧数
- いいね数
- 質問内容
- 値下げ履歴
- 次回改善
```

検証対象:

- [ ] HOTEL JOY
- [ ] メルカリ出品
- [ ] Booking返信
- [ ] 経理
- [ ] 投資
- [ ] 人体ログ
- [ ] AI Workspace OS

Promotion Rule:
3〜5分野で、Goalからシステム化までの抜け漏れが減るならPrinciple Candidateとして検討する。

既存構造との関係:
- Workspace Routerは、どのWorkspaceで作業するかを選ぶ。
- Mission Valueは、Human Agent Missionの価値を評価する。
- Human Agent Cognitive Flowは、Human Agentが自然に動ける受け取り順を設計する。
- Goal-to-System Blueprintは、Goalから必要な能力、役割、場所、成果物、実行、承認、学習までを一気通貫で並べる。

自己レビュー:
- Layer Leak: なし。AI Workspace OS Project内のFuture Candidateとして保存する。
- Kernel混入: なし。まだ複数分野で検証されていない。
- 概念増加: 注意が必要。独立Engine化せず、Future CandidateとしてEvidenceで育てる。
- 既存構造との重複: Workspace Router、Mission Value、Human Agent Cognitive Flowと接続するが、現時点では上位実装にしない。

### Future Candidate自己レビュー
Layer Leak:
Future CandidateはProject内の検証テーマとして管理しており、Kernel、Principle、AI_CONTEXTには入れていない。

責務:
Future Candidate管理は、採用前の仮説をEvidenceで育てるための運用である。
判断基準そのものではない。

Kernel混入:
毎回AIが読むべき最小手順ではないため、Kernelへ入れない。

AGENTS / AI_CONTEXT:
現時点では実運用で必ず読む情報ではないため、追記しない。

概念増加:
新しい概念を増やすためではなく、昇格前の候補を保留し、Evidence不足のままCore化しないための管理である。
