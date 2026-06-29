# 07_AGENTS README

## 目的
このフォルダは、MR Brainを運用するAI Agentの役割定義を保存する場所。

Agentは機能ではなく、MR Brainの運用責任を分担するための人格・役割である。

## このファイルが必要な理由
MR Brain内のAgent一覧と役割境界を明確にするため。

Agentが増えすぎると管理が複雑になるため、このREADMEを入口にして「どのAgentが何を担当するか」を確認する。

## 将来利用するAgent
- Brain Curator Agent: Agent定義の重複や増えすぎを確認する
- Compass Agent: 今必要なAgentだけを選ぶ
- Identity Agent: 自分理解に関係するAgent定義を参照する
- Decision Agent: 重要判断を扱うAgentの責任範囲を確認する
- CEO Agent: 事業管理に関係するAgentを選ぶ
- Builder Agent: 実装やGitHub連携に関係するAgentを選ぶ

## 既存ファイルとの関係
- 新規作成: `07_AGENTS` の入口として新規作成
- 参照: `AGENTS.md` はCodexが作業前に読む実行ルール
- 参照: `07_SYSTEM/AI_CONTEXT.md` は全AI共通の背景
- 参照: `00_HOME/樫原義大OS設計書.md` はAgent設計の上位目的
- 統合候補: 将来、`AGENTS.md` と `07_AGENTS/README.md` の重複は「作業ルール」と「Agent一覧」に分けて整理する

## このフォルダに入れるもの
- Agentごとの目的
- 読むべきファイル
- 判断基準
- やること
- やらないこと
- 出力テンプレート

## 入れてはいけないもの
- 日々のメモ
- 個人情報の詳細
- 税務・契約・給与情報の原本
- 実装コード

## 基本Agent構想
| Agent | 役割 |
|---|---|
| Brain Curator Agent | 情報整理、重複排除、索引、Archive候補管理 |
| Identity Agent | 樫原義大の価値観、傾向、判断基準、ワクワク源の整理 |
| Decision Agent | 意思決定、判断理由、やめた案、リスクの記録 |
| CEO Agent | JOY、孝行、経理、税務、スタッフ、契約、設備の経営視点整理 |
| Builder Agent | Codex、GitHub、アプリ、スプレッドシート連携の実装整理 |
| Compass Agent | 優先順位、方向性、寄り道、現在地の確認 |
| Communication Agent | 返信、依頼、クレーム対応、スタッフ指導、AI指示の文章整理 |
| Flow Bridge Agent | 発見、保存、調査、AI指示、現実で試す次の1手を接続 |
| Blueprint Agent | 目的、現在地、完成形、必要部品、実装手順の設計図を作る |
| Blueprint Reviewer | Blueprintを実装前に確認し、シンプルさ、接続漏れ、循環、リスクを確認する |
| SNS Posting Engine | 接続・循環・適応の判断原理をSNS投稿へ変換し、外部反応をMrBrainへ戻す |

## 運用ルール
- Agentを増やしすぎない
- 役割が重複したら統合を検討する
- 人を評価するために使わない
- 判断基準と設計意図を優先する
- 実行前に提案する

## 最初に作るAgent
Phase 1では次の2つだけ定義する。

- [[07_AGENTS/Brain Curator Agent]]
- [[07_AGENTS/Compass Agent]]

## 定義済みAgent
- [[07_AGENTS/Identity Agent]]
- [[07_AGENTS/Communication Agent]]
- [[07_AGENTS/Flow Bridge Agent]]
- [[07_AGENTS/Blueprint Agent]]
- [[07_AGENTS/Blueprint Reviewer]]
- [[07_AGENTS/SNS Posting Engine]]

## 今後追加候補
- `Decision Agent.md`
- `CEO Agent.md`
- `Builder Agent.md`
