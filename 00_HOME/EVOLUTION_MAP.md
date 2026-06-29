# MrBrain Evolution Map

## 目的
MrBrainの進化を、commit履歴ではなく「ProjectのFlowがどこまで接続され、次にどこへエネルギーを使う価値が最も高いか」で判断する。

Gitは保存手段。
Evolution Mapは、進化管理の正本である。

見るべきことは、能力数ではない。

```md
今どこがボトルネックか
そこを改善すると、全体の循環がどれだけ良くなるか
今やる価値が一番高い理由は何か
```

## 現在のVersion
```md
MrBrain v0.5
```

現在地:
- GitHub保存とSnapshot復元は接続済み
- Kernel RouterとLayer Integrity Checkは接続済み
- Evolution MapはFlow Decision Dashboardへ移行
- 次は、Priority 1のFlowを現実データで進める段階

## Flow Decision Dashboard
| Priority | Project | Flow | Current Position | Next Bottleneck | Expected Return | Confidence | Evidence | Next Best Action | Snapshot | Git Tag | Last Updated |
|---:|---|---|---|---|---|---|---|---|---|---|---|
| 1 | JOY ホテルOS | Signal → Event → Pricing → Sales → Accounting → Tax | Signal取得Blueprintはあるが、現場信号の実データがまだない | Signal | ★★★★★ | 80% | 売上源流がSignalにあるため。信号取得方式が未確認なのでConfidenceは80%。 | 202号室を代表点にして、操作前後のPC画面、入力機器、料金表示を撮る | 未設定 | 未設定 | 2026-06-29 |
| 2 | 会社運営OS / 経理 | Input → Approval → Monthly Closing → Tax Export → Filing | DB正本 + 人間承認の方向は決定。1か月テスト範囲が未確定 | Input正本 | ★★★★★ | 75% | DB正本ができると月次・税務へ接続できるため。最小DB項目が未確定なのでConfidenceは75%。 | DB正本 + 人間承認の1か月テスト範囲を確定する | 未設定 | 未設定 | 2026-06-29 |
| 3 | MrBrain Core | 起動 → Routing → Layer確認 → Git保存 → Snapshot復元 | GitHub保存、Snapshot復元、AGENTS導線は接続済み。実運用テストが未完了 | Snapshot運用の実使用 | ★★★★☆ | 90% | GitHub保存と復元ルールは実装済み。実際の大きな編集で未使用なのでConfidenceは90%。 | 次の大きな編集で、編集前後commitとsnapshotを1回実際に使う | `snapshot-20260629-mrbrain-github-initial-sync` | `snapshot-20260629-mrbrain-github-initial-sync` | 2026-06-29 |
| 4 | スプレッドシート整理 | Source → Index → Master → AI Handoff → DB移行 | 5シート索引はある。会社マスターの正本候補がまだ未検証 | Master正本 | ★★★★☆ | 80% | 会社マスターが決まると経理・税務・AI引き継ぎが安定するため。正本候補の再確認が未完了。 | 5スプレッドシートの会社マスター正本候補を再検証する | 未設定 | 未設定 | 2026-06-29 |
| 5 | Human Communication OS | Principle → Template → Real Reply → Feedback → Skill化 | 原則とテンプレートはある。実際の返信でまだ検証していない | Real Reply | ★★★☆☆ | 85% | 原則とテンプレートは揃っているため。実際の返信で未検証なのでConfidenceは85%。 | 実際の問い合わせ文を1つテンプレートに当てはめる | 未設定 | 未設定 | 2026-06-29 |
| 6 | NotebookLM / AI学習 | Source → Compression → Connection → Learning → Automation | NotebookLMの役割は整理済み。MrBrainへ戻す運用が未定着 | Learning | ★★★☆☆ | 80% | 使い分けは整理済み。重要メモをMrBrainへ戻す実運用回数が不足している。 | NotebookLMで得た重要メモをMrBrainへ1回保存する | 未設定 | 未設定 | 2026-06-29 |
| 7 | Approval Inbox / Command Center | Intake → Classification → Proposal → Approval → Execution → Learning | 汎用コンポーネントは整理済み。最初の適用例が未決定 | Intake | ★★★★☆ | 60% | 承認画面化の波及は大きい。最初の入口Projectが未確定なのでConfidenceは60%。 | 最初の適用例をBooking.com / メール / 経理確認のどれにするか1つ決める | 未設定 | 未設定 | 2026-06-29 |
| 8 | 投資家OS | Root Structure → Value → Network → Prediction → Execution | 思想と会社カード構想はある。Networkと予測の実装は未着手 | Network | ★★★★☆ | 65% | Network完成は予測精度へ効く。現在GoalがJOY・経理優先なのでConfidenceは65%。 | 会社カードMVPを今進めるか保留するか判断する | 未設定 | 未設定 | 2026-06-29 |

## 評価基準
### Expected Return
Expected Returnは、時間短縮ではなく、循環改善量で評価する。

| 評価 | 意味 |
|---|---|
| ★★★★★ | ここがつながると、後続Flowが一気に動く |
| ★★★★☆ | 複数Projectへ波及し、かなり大きく循環が改善する |
| ★★★☆☆ | 使う頻度は高いが、波及範囲は限定的 |
| ★★☆☆☆ | 局所改善。今すぐでなくてもよい |
| ★☆☆☆☆ | 効果が小さい、または保留でよい |

### Confidence
Confidenceは、Next Bottleneck判断への確信度である。

```md
90%以上: ほぼ確実
70〜89%: 十分に妥当
50〜69%: 価値はあるが情報不足
50%未満: 先に確認が必要
```

### Priority
Priorityは、Expected Returnだけでは決めない。

次を総合して決める。

- Expected Return
- Confidence
- 現在のGoal
- 他Projectへの波及効果
- エネルギーコスト

## Priority一覧
| Priority | Project | Next Bottleneck | Expected Return | Confidence | 優先理由 |
|---:|---|---|---|---|---|
| 1 | JOY ホテルOS | Signal | ★★★★★ | 80% | 売上源流がつながると、Pricing、Sales、Accounting、Taxまで後続Flowが動くため |
| 2 | 会社運営OS / 経理 | Input正本 | ★★★★★ | 75% | 経理、承認、月次、税務の土台になるため |
| 3 | MrBrain Core | Snapshot運用の実使用 | ★★★★☆ | 90% | AI編集の安全性が上がり、全Projectの復元性が上がるため |
| 4 | スプレッドシート整理 | Master正本 | ★★★★☆ | 80% | 会社情報の正本が決まると、経理、税務、AI引き継ぎが安定するため |
| 5 | Human Communication OS | Real Reply | ★★★☆☆ | 85% | テンプレートを実用に接続すると、接客・返信の摩擦が下がるため |
| 6 | NotebookLM / AI学習 | Learning | ★★★☆☆ | 80% | 学習結果をMrBrainへ戻せると、同じ理解の繰り返しが減るため |
| 7 | Approval Inbox / Command Center | Intake | ★★★★☆ | 60% | 将来価値は高いが、最初の入口が未確定で情報不足のため |
| 8 | 投資家OS | Network | ★★★★☆ | 65% | 価値は高いが、現在の最優先GoalであるJOY・経理から離れるため |

## 最優先ボトルネック
現時点で最も循環改善が大きい場所:

```md
JOY ホテルOS / Signal
```

理由:
- 売上承認、月次集計、経理、税務は、売上源流が取れないと流れない
- SignalがEvent化できると、Pricing、Sales、Accounting、Taxへ接続できる
- 202号室を代表点にすれば、全14部屋へ展開できる可能性がある
- 会社運営OS / 経理にも波及する

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
| 2 | 会社運営OS / 経理 | Input → Approval | 1か月分の最小DB正本テスト範囲が決まる | `after-YYYYMMDD-accounting-approval-test` |
| 3 | MrBrain Core | Git保存 → Snapshot復元 | 大きな編集前後でsnapshotを1回使う | `after-YYYYMMDD-mrbrain-snapshot-operation` |
| 4 | Human Communication OS | Template → Real Reply | 実際の問い合わせ返信を1件作り、結果を記録する | `after-YYYYMMDD-human-communication-first-reply` |

## Versionの考え方
| Version | Flow状態 |
|---|---|
| v0.1 | VaultとAI入口ができた |
| v0.2 | Runtime Loopで循環の考え方が入った |
| v0.3 | Kernel Routerで最小読み込みとRoutingができた |
| v0.4 | GitHub保存とSnapshot復元ができた |
| v0.5 | Flow Decision Dashboardで、Projectごとの詰まり、期待リターン、確信度、優先度が見える |
| v0.6 | JOY Signal → Event が現実データで接続される |

## 運用ルール
- Evolution Mapは、Flow Decision Dashboardとして使う
- Projectごとに、Current Position、Next Bottleneck、Expected Return、Confidence、Priority、Next Best Actionを1つに絞る
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
  - Evolution Mapには、詰まり、評価、次の1手だけを書く

この変更は、新しいPrincipleではない。
既存の接続・循環・適応の考え方を、Project判断の精度向上に使う運用レイヤーである。
