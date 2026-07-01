# AI Workspace OS Dry Run

作成日: 2026-07-01

## 目的

このDry Runは、新しいFuture Candidate、Engine、Principleを追加するためのものではない。

目的は、現在のAI Workspace OSが、HOTEL JOYの「ホテルを一気通貫で自動運営する」というScenarioで、最初から最後まで止まらず回るかを確認することである。

検証する流れ:

```md
Intent
↓
Goal Validation Gate
↓
Goal
↓
Workspace Router
↓
Reality
↓
Reality Model
↓
Capability
↓
Decision
↓
Artifact
↓
Approval
↓
Execution
↓
Learning
↓
MrBrain更新
↓
次Mission
```

## Scenario

Humanの最初の発話:

```md
HOTEL JOYを全部自動化したい
```

これはGoalではなく、Intentとして扱う。

## Layer Trace

| Layer | 入力 | 処理 | 出力 | 担当 | Workspace | 成果物 |
|---|---|---|---|---|---|---|
| Intent | HOTEL JOYを全部自動化したい | 願望、違和感、方向性として受け取る | Intent: HOTEL JOYの運営負荷を下げたい | Human | ChatGPT | 初期相談 |
| Goal Validation Gate | Intent | Goal、Success Condition、Scope、Reality制約を確認 | 今回のGoal候補を分解 | AI Agent | ChatGPT | Goal確認リスト |
| Goal | Goal候補 | 最初に進むGoalを1つに絞る | Goal: 信号・料金・売上源流を理解する | Human承認 + AI Agent | ChatGPT | 確定Goal |
| Workspace Router | 確定Goal | 作業場所を選ぶ | ChatGPTで整理、Codexで保存、Driveで原本保管 | AI Agent | ChatGPT / Codex / Drive | Workspace選定 |
| Reality | HOTEL JOY現場 | 現実で何が動いているかを読む | 部屋信号、PC入力、料金、部屋State、売上 | Human Agent + AI Agent | 現場 / Drive / ChatGPT | Realityメモ |
| Reality Model | Reality Evidence | 現実を構造化する | Signal → Event → Rule → State → Output | AI Agent | ChatGPT / MrBrain | Reality Model |
| Capability | Reality Model | 影響を与える能力を選ぶ | Signal Understanding、Pricing Rule Extraction、State Modeling、Mission Generation | AI Agent | ChatGPT / MrBrain | Capability一覧 |
| Decision | Capability | 次に何を実行すべきか決める | Representative Evidence Setを集める | AI Agent | ChatGPT | Decision |
| Artifact | Decision | Humanが動ける形へ変換 | Human Agent Mission Sheet、LINE文、写真チェックリスト | AI Agent | ChatGPT / Codex | Mission Artifact |
| Approval | Artifact | 実行前に承認する | HumanがMission実行を承認 | Human | ChatGPT / LINE想定 | 承認 |
| Execution | 承認済みMission | 現場Evidenceを集める | PC裏写真、入力機器写真、キーボード写真、料金表、操作前後画面 | Human Agent | 現場 / Google Drive / LINE想定 | Evidence |
| Learning | Evidence | AIが解析し、理解度と不足を返す | 理解度、Gap、次Mission | AI Agent | ChatGPT / MrBrain | Analysis Note |
| MrBrain更新 | Learning | 正本へ戻す | Blueprint、Evidence、Decision Log相当、Next Mission | Codex | MrBrain / GitHub | Project更新 |
| 次Mission | Gap | 最小Human Costで次のEvidenceを選ぶ | 例: 料金切替条件だけ追加確認 | AI Agent | ChatGPT / LINE想定 | 次Mission |

## Goal Validation

Intent:

```md
HOTEL JOYを全部自動化したい
```

このままExecutionへ流すと広すぎる。

Goal Validationで確認する。

| 確認項目 | Dry Run上の判断 |
|---|---|
| Goalは明確か | 不十分。「全部自動化」は広すぎる |
| Success Conditionは測定できるか | 不十分。どこまでできたら成功か不明 |
| Scopeは適切か | 広すぎる |
| Humanが本当に望んでいる状態か | おそらく「運営判断と手作業を減らしたい」 |
| Realityと矛盾していないか | 既存PC、信号、料金、現場制約が未確認 |

Goal候補:

- 信号理解
- 料金ルール理解
- 部屋State理解
- 売上発生源流理解
- スタッフ管理
- 予約管理
- 全体OS化

最初のGoal:

```md
HOTEL JOYの売上源流である、信号・料金・部屋State・売上Eventを7〜8割推定できる状態にする。
```

Success Condition:

```md
PC裏、入力機器、キーボード、料金表、操作前後画面から、
Signal → Event → Rule → State → Outputの流れを7〜8割推定できる。
```

## Timeline

| 時間軸 | 状態 | 待機 | 次に進む条件 |
|---|---|---|---|
| T0 | HumanがIntentを話す | なし | OSがGoal Validationする |
| T1 | Goal候補を分解 | Human承認待ち | 最初のGoalを1つ選ぶ |
| T2 | Workspace選定 | なし | ChatGPT / Codex / Driveの役割が決まる |
| T3 | Human Agent Mission生成 | Approval待ち | HumanがMission実行を承認 |
| T4 | 現場Evidence収集 | Human Agent待ち | 写真、料金表、画面が集まる |
| T5 | Evidence保管 | Drive保存待ち | 原本がDriveに入り、MrBrainに索引できる |
| T6 | AI解析 | AI解析待ち | 理解度とGapが出る |
| T7 | Learning | Codex編集待ち | MrBrainへ結果を戻す |
| T8 | 次Mission生成 | Human承認待ち | 次の最小Missionが決まる |

## Waiting Point

| Waiting Point | 内容 | 発生しやすさ |
|---|---|---|
| Human待ち | Goal承認、Mission承認、現場判断 | 高 |
| 写真待ち | PC裏、入力機器、キーボード、画面、料金表 | 高 |
| LINE返信待ち | Human AgentからEvidenceが戻るまで | 中 |
| Approval待ち | 現場操作前、外部送信前、既存システム影響前 | 高 |
| API待ち | 将来APIを使う場合 | 低 |
| Browser Automation待ち | APIがない場合の半自動操作 | 低〜中 |
| Codex編集待ち | MrBrain保存、Git保存 | 中 |
| AI解析待ち | Evidenceから構造推定 | 中 |

## Block Point

| Block Point | 止まる原因 | 対応 |
|---|---|---|
| Goalが曖昧 | 「全部自動化」が広すぎる | Goal ValidationでScopeを切る |
| Reality不足 | 現場信号、入力機器、料金表が不明 | Representative Evidence Setを集める |
| Evidence不足 | 写真や画面が足りない | Gapだけ返し、次Missionを小さく出す |
| Capability不足 | 画像解析、料金抽出、状態推定が弱い | Human Agent追加確認かNotebookLM / AI解析へ回す |
| Decision不能 | 何から実行すべきか決められない | Success Conditionへ戻る |
| Approval不足 | 外部影響があるのに承認がない | Approval Gateで停止 |
| Execution不可 | APIなし、画面操作不可、規約不明 | Human Agent実行または手動運用に戻す |
| Learning不足 | 結果をMrBrainへ戻していない | CodexでProject更新、Git保存 |

## Merge確認

Dry Run上、新しいLayerは不要。

Mergeできそうなもの:

- Artifactは独立Layerにせず、現時点ではDecision後の出力形式として扱える。
- ApprovalはCore Layerではなく、Execution前のGateとして扱える。
- Representative Evidence SetはReality Modelへ入る前のEvidence選定として扱える。

不要に見えるもの:

- なし。ただし、Capability RouterはこのDry Runでも独立して出てこない。Capability Registry内部の選択機能で足りる可能性が高い。

## Human Cost

Humanが本当に必要な作業:

1. 最初のGoal承認
2. 現場で写真を撮る
3. 料金表を撮る、または手書きで渡す
4. 操作前後の画面変化を記録する
5. 配線や設定には触らない判断を守る
6. AIが出した次Missionを承認する
7. 外部影響があるExecutionを承認する

Humanがやらなくてよい作業:

- 全体設計
- Layer分類
- Blueprint作成
- Evidenceの意味づけ
- Capability選択
- Decision整理
- Artifact形式選択
- Learning整理

一番Human Costが高い場所:

```md
現場Evidence収集
```

理由:
現場に行く、写真を撮る、画面変化を見る、送る、という物理行動が必要だから。

## AI Cost

AI側が担当する処理:

- IntentをGoal候補へ分解
- Success Conditionの設定
- Scopeの切り出し
- Workspace選定
- Reality Model作成
- Capability一覧化
- Decision生成
- Human Agent Mission生成
- LINE文生成
- A4指示書生成
- Evidence解析
- 理解度推定
- Gap Analysis
- 次Mission生成
- MrBrain更新案作成
- Git保存支援

一番AIが価値を出す場所:

```md
EvidenceからReality Model、Capability、Decisionへ変換する部分
```

理由:
Humanが撮った写真や料金表を、Signal / Event / Rule / State / Outputへ変換し、次の一手まで出せるから。

## Reality Change

Execution後に変わるReality:

| Execution | Reality Change | 意味 |
|---|---|---|
| Human AgentがPC裏写真を撮る | 入力経路の推定精度が上がる | あり |
| 料金表を撮る | Pricing Rule推定が進む | あり |
| 操作前後画面を撮る | Event / State変化が見える | あり |
| AIがMissionを作るだけ | 現実はまだ変わらない | 準備としては意味あり |
| MrBrainへ保存する | 次回AIの開始位置が変わる | 間接的なReality Change |
| 承認なしで外部送信する | 危険 | 実行禁止 |

Realityが変わらないExecutionの扱い:

現実が直接変わらないExecutionでも、次のReality Changeを起こすための準備なら意味がある。

例:
- Mission生成
- Blueprint作成
- Evidence整理

ただし、準備だけで止まり続ける場合は循環していない。

## Learning

MrBrainへ戻す情報:

- 確定Goal
- Success Condition
- 取得したEvidenceの索引
- AIが推定したReality Model
- 理解度
- Gap
- 次Mission
- Waiting Point
- Block Point
- Human Costが高かった箇所
- AIが価値を出した箇所
- Approvalが必要だった箇所

MrBrainへ保存しない情報:

- 写真、動画、スクショの原本
- 個人情報、秘密情報、契約書、証憑の原本
- 長いチャット全文
- 一時的な雑談

原本の扱い:

```md
Google Drive:
写真、動画、スクショ、証憑、契約書の原本

MrBrain:
要約、索引、判断、Blueprint、Next Mission

GitHub:
MrBrainの履歴と復元
```

## 最終ビジョン評価

問い:
AI Workspace OSは、本当に「Humanは目的だけ話し、OSが最適な成果物を組み立て、Humanは承認だけする」という最終ビジョンへ到達できる構造になっているか。

評価:
構造としては到達可能。

ただし、現時点ではまだ完全ではない。

到達できる理由:
- IntentをGoal Validation Gateで安全にGoalへ変換できる。
- Reality Modelで対象世界を理解できる。
- Capability Registryで「できること」と実装方法を分離できる。
- Decision Engineで次に何をすべきかを決められる。
- Execution OSで現実変更とApprovalを扱える。
- LearningでMrBrainへ戻せる。

まだ弱い理由:
- Artifactの自動選択は実案件検証が少ない。
- Waiting Point管理はまだ手動に近い。
- Approval UIがまだ実装されていない。
- Human AgentからEvidenceが戻る導線がまだ完全ではない。
- Executionは多くがHuman Agent依存で、API / Browser Automationは未検証。

結論:
AI Workspace OSは「考えるOS」から「成果物を生み出すOS」へ進化し始めている。
ただし、現在の中心はまだDry RunとHuman-in-the-loopである。

## Dry Runまとめ

① 一番止まりそうな場所:

```md
現場Evidence待ち
```

理由:
AIだけではRealityを観測できず、Human Agentの写真、料金表、画面変化が必要だから。

② 一番美しかったFlow:

```md
Intent
↓
Goal Validation
↓
Representative Evidence Set
↓
Human Agent Mission
↓
AI解析
↓
次Mission
```

理由:
Humanは大きな願望を話すだけで、OSが小さな実行Missionへ変換できている。

③ 一番Human Costが高かった場所:

```md
現場での写真・画面・料金表収集
```

理由:
物理的に動く必要があるため。

④ 一番AIが価値を出した場所:

```md
EvidenceをReality Modelへ変換し、Decisionと次Missionを出す部分
```

理由:
Humanが見ても意味づけしづらい情報を、構造と次の一手へ変換できるから。

⑤ 一番改善効果が高い箇所:

```md
Human Agent Missionの品質向上
```

理由:
ここが良くなると、Human Costが下がり、Evidence品質が上がり、AI解析と次Missionが一気に改善する。

⑥ Next Best Action:

```md
HOTEL JOYの最初のHuman Agent Missionを、Goal Validation済みの「信号・料金・部屋State・売上源流理解」に絞って実行する。
```

## 自己レビュー

Layer Leak:
なし。このDry RunはAI Workspace OS Project内の検証レポートであり、Kernel / Principle / AI_CONTEXT / AGENTSには触れていない。

責務重複:
大きな重複はなし。Artifactは独立Layerにせず、Decision後の成果物形式として扱った。

Operation肥大化:
注意が必要。Workspace、Approval、Git、Mission、Learningが増えやすい。実案件ではNext Best Actionを1つに絞る必要がある。

Project依存:
HOTEL JOY依存が強い。このDry Run結果を投資、Booking、メルカリ、経理で再検証するまでCore昇格しない。

Timeline不足:
待機状態を入れたことで、Human Agent待ち、写真待ち、Approval待ちが明確になった。

Waiting管理:
現時点では手動管理。将来的にはEvolution MapやApproval Inboxで管理する必要があるが、今回は新概念化しない。

Approval管理:
外部送信、既存システム影響、金銭、個人情報が絡む箇所でApprovalが必要。Dry Run上は妥当。

Architectureとの整合性:
整合している。Goal Validation Gate、Reality Model、Capability、Decision、Execution、Learningの順で止まらず通せる。

新しい概念:
追加していない。既存ArchitectureのDry Runとして保存する。
