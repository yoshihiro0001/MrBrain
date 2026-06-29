# MrBrain Evolution Map

## 目的
MrBrainの進化を、commit履歴ではなく「ProjectのFlowがどこまで接続されたか」で追う。

Gitは保存手段。
Evolution Mapは、進化管理の正本である。

見るべきことは、能力数ではない。

```md
今どこがボトルネックか
次にどこへエネルギーを使えば、最も循環改善が大きいか
```

## 現在のVersion
```md
MrBrain v0.4
```

現在地:
- GitHub保存とSnapshot復元は接続済み
- Kernel RouterとLayer Integrity Checkは接続済み
- 次は、各ProjectのFlowを現実で1つずつ進める段階

## Flow Progress Dashboard
| Project | Flow | Progress | Next Bottleneck | Next Best Action | Snapshot | Git Tag | Last Updated |
|---|---|---|---|---|---|---|---|
| MrBrain Core | 起動 → Routing → Layer確認 → Git保存 → Snapshot復元 | `Boot ████████`<br>`Router ████████`<br>`Layer ████████`<br>`Git ████████`<br>`Snapshot ██████░░` | Snapshot運用の実使用 | 次の大きな編集で、編集前後commitとsnapshotを1回実際に使う | `snapshot-20260629-mrbrain-github-initial-sync` | `snapshot-20260629-mrbrain-github-initial-sync` | 2026-06-29 |
| JOY ホテルOS | Signal → Event → Pricing → Accounting → Tax | `Signal ████░░░░`<br>`Event ██░░░░░░`<br>`Pricing ██░░░░░░`<br>`Accounting ░░░░░░░░`<br>`Tax ░░░░░░░░` | Signal | 202号室を代表点にして、操作前後のPC画面、入力機器、料金表示を撮る | 未設定 | 未設定 | 2026-06-29 |
| 会社運営OS / 経理 | Input → Approval → Monthly Closing → Tax Export → Filing | `Input ███░░░░░`<br>`Approval ██░░░░░░`<br>`Monthly █░░░░░░░`<br>`Tax Export █░░░░░░░`<br>`Filing ░░░░░░░░` | Input正本 | DB正本 + 人間承認の1か月テスト範囲を確定する | 未設定 | 未設定 | 2026-06-29 |
| スプレッドシート整理 | Source → Index → Master → AI Handoff → DB移行 | `Source ████████`<br>`Index ██████░░`<br>`Master ████░░░░`<br>`AI Handoff ████░░░░`<br>`DB移行 ░░░░░░░░` | Master正本 | 5スプレッドシートの会社マスター正本候補を再検証する | 未設定 | 未設定 | 2026-06-29 |
| NotebookLM / AI学習 | Source → Compression → Connection → Learning → Automation | `Source ████████`<br>`Compression ██████░░`<br>`Connection ████░░░░`<br>`Learning ██░░░░░░`<br>`Automation ░░░░░░░░` | Learning | NotebookLMで得た重要メモをMrBrainへ1回保存する | 未設定 | 未設定 | 2026-06-29 |
| Human Communication OS | Principle → Template → Real Reply → Feedback → Skill化 | `Principle ████████`<br>`Template ██████░░`<br>`Real Reply ██░░░░░░`<br>`Feedback ░░░░░░░░`<br>`Skill化 ░░░░░░░░` | Real Reply | 実際の問い合わせ文を1つテンプレートに当てはめる | 未設定 | 未設定 | 2026-06-29 |
| 投資家OS | Root Structure → Value → Network → Prediction → Execution | `Root ████████`<br>`Value ██████░░`<br>`Network ███░░░░░`<br>`Prediction ░░░░░░░░`<br>`Execution ░░░░░░░░` | Network | 会社カードMVPを今進めるか保留するか判断する | 未設定 | 未設定 | 2026-06-29 |
| Approval Inbox / Command Center | Intake → Classification → Proposal → Approval → Execution → Learning | `Intake ██░░░░░░`<br>`Classification ██░░░░░░`<br>`Proposal █░░░░░░░`<br>`Approval ░░░░░░░░`<br>`Execution ░░░░░░░░`<br>`Learning ░░░░░░░░` | Intake | 最初の適用例をBooking.com / メール / 経理確認のどれにするか1つ決める | 未設定 | 未設定 | 2026-06-29 |

## 最優先ボトルネック
現時点で最も循環改善が大きい場所:

```md
JOY ホテルOS / Signal
```

理由:
- 売上承認、月次集計、経理、税務は、売上源流が取れないと流れない
- 202号室を代表点にすれば、全14部屋へ展開できる可能性がある
- ここがつながると、ホテルOS、会社運営OS、経理OSが同時に前進する

Next Best Action:
```md
202号室で1つだけ操作し、操作前後のPC画面、料金表示、伝票、PC裏、入力機器、キーボード型番、デバイスマネージャー、料金表を撮る。
```

## Snapshot対応表
Snapshotを作る時は、単に保存しない。

必ず、改善したFlowと戻る目的を対応付ける。

| Snapshot名 | 改善したFlow | 改善した理由 | 戻る目的 | Git Tag | 対応commit |
|---|---|---|---|---|---|
| `snapshot-20260629-mrbrain-github-initial-sync` | MrBrain Core / Git保存・Snapshot復元 | AI編集後に戻せる状態を作るため | Git導入や復元ルール周辺で壊れた時、この安定地点へ戻る | `snapshot-20260629-mrbrain-github-initial-sync` | `a413c33` |

## Snapshot記録テンプレート
```md
## Snapshot記録
- Snapshot名:
- 改善したFlow:
- 改善した理由:
- 戻る目的:
- Git Tag:
- 作成日:
- 対応commit:
- 関連Project:
- 関連ファイル:
```

## 次に育てるFlow
| 優先 | Project | 育てるFlow | 成功条件 | Snapshot候補 |
|---:|---|---|---|---|
| 1 | JOY ホテルOS | Signal → Event | 202号室の1操作について、現場動作からPC処理までの対応表ができる | `after-YYYYMMDD-joy-202-signal-event` |
| 2 | MrBrain Core | Git保存 → Snapshot復元 | 大きな編集前後でsnapshotを1回使う | `after-YYYYMMDD-mrbrain-snapshot-operation` |
| 3 | 会社運営OS / 経理 | Input → Approval | 1か月分の最小DB正本テスト範囲が決まる | `after-YYYYMMDD-accounting-approval-test` |
| 4 | Human Communication OS | Template → Real Reply | 実際の問い合わせ返信を1件作り、結果を記録する | `after-YYYYMMDD-human-communication-first-reply` |

## Versionの考え方
| Version | Flow状態 |
|---|---|
| v0.1 | VaultとAI入口ができた |
| v0.2 | Runtime Loopで循環の考え方が入った |
| v0.3 | Kernel Routerで最小読み込みとRoutingができた |
| v0.4 | GitHub保存とSnapshot復元ができた |
| v0.5 | Flow Progress Dashboardで、Projectごとの詰まりと次の1手が見える |
| v0.6 | JOY Signal → Event が現実データで接続される |

## 運用ルール
- Evolution Mapは、能力一覧ではなくFlow Progress Dashboardとして使う
- Projectごとに、Flow、Progress、Next Bottleneck、Next Best Actionを1つに絞る
- Gitは保存、Evolution Mapは進化管理
- Snapshotを作ったら、改善したFlow、改善理由、戻る目的を記録する
- 迷ったら「どの日付に戻るか」ではなく「どのFlowに戻るか」で判断する

## Layer確認
- Kernel:
  - 実行手順そのものは `07_SYSTEM/MrBrain Kernel Router.md` に置く
  - Evolution Mapには入れすぎない
- Library:
  - Root Structure、Leverage Point、接続理論などの説明は `02_PRINCIPLES` に置く
  - Evolution Mapは説明書ではなく進捗表として使う
- Project:
  - 具体的な確認項目やBlueprintは `04_PROJECTS` に置く
  - Evolution Mapには、詰まりと次の1手だけを書く

この変更は、新しいPrincipleではない。
既存の接続・循環・適応の考え方を、Project進捗の見える化に使う運用レイヤーである。
