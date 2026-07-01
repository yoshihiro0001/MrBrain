# JOY システム再構築 情報収集インターフェース

## 目的
HOTEL JOYのホテルシステムを再構築するために必要な情報を、IT知識がないHuman Agentでも、最小の負担で漏れなく集める。

これは調査票ではない。
信号、料金、部屋状態、PC入力、イベント、配線、設備を、AIが7〜8割推定するための情報収集インターフェースである。

このミッションの目的は、HOTEL JOY OSの循環を進めること。

Human Agentは、現場でしか取れない写真、メモ、料金表、画面変化を集める。
AI Agentは、その材料から信号、料金、状態、売上、DB、画面を推定する。

## 成功条件
このシートだけで、次の流れを推定できること。

```md
現場操作
↓
信号 / 入力
↓
PC上の反応
↓
部屋状態
↓
料金
↓
売上イベント
↓
自社OS設計
```

## A4印刷ルール
- A4縦
- 1部屋につき1枚
- チェック中心
- 写真貼付OK
- 手書きOK
- 専門用語を増やさない
- 分からない項目は空欄でよい
- 配線や設定は触らない

---

# JOY Human Agent Mission Sheet

対象部屋: □ 202　□ その他（　　　）

日付:　　　　　Human Agent:　　　　　確認時間:　　　　　

## Human Agent Mission
このミッションは、HOTEL JOY OSを進化させるための現場ミッションである。

Human Agent:
現場でしか取れない情報を集める人。

AI Agent:
集まった情報から、次を推定する存在。

- Input
- Event
- Rule
- State
- Output
- 不足情報
- 次のミッション

このミッションで進む循環:

```md
Signal
↓
Event
↓
Rule
↓
State
↓
Output
```

今回の目標:
HOTEL JOY OS再構築に必要な情報を70〜80%見える化する。

数字は目安であり、完璧を目指さない。

## 1. 🎯 今日のゴール
□ 1つの部屋で、操作した時にPCで何が変わるかを見る

□ 料金、状態、画面、伝票、音声の変化を記録する

□ パソコンまわりの写真を撮る

完了条件:
□ 操作前と操作後の違いが分かる

---

## 2. 📷 まず撮るもの
| チェック | 撮るもの | 目的 |
|---|---|---|
| □ | PCの後ろ全体 | 何がつながっているか見る |
| □ | キーボード全体 | 専用入力か見る |
| □ | キーボード裏の型番 | 機種を特定する |
| □ | 黒い箱、ハブ、変換器 | 信号の入口を探す |
| □ | ケーブルの差し込み口 | USB / LAN / 丸い端子などを見る |
| □ | 既存システムの画面 | 部屋状態の表示を見る |
| □ | 料金表 | 料金計算のルールを見る |
| □ | 伝票や売上画面 | 売上への反映を見る |

写真貼付欄:

```md
1. PC後ろ:
2. 入力機器:
3. キーボード型番:
4. 既存画面:
5. 料金表:
6. 伝票:
```

---

## 3. 👀 操作前に見る
| チェック | 見るもの | メモ |
|---|---|---|
| □ | 部屋番号 | 例: 202 |
| □ | 部屋状態 | 空室 / 利用中 / 清掃中 |
| □ | 表示料金 | 円 |
| □ | 経過時間 | 時間 |
| □ | 画面の色 | 例: 赤 / 青 / 黄 |
| □ | 音声 | あり / なし |

操作前メモ:

```md

```

---

## 4. 🕹️ 1つだけ操作する
最初は1つだけ選ぶ。

| チェック | 操作 | 何を見るか |
|---|---|---|
| □ | 入室 | 時間が始まるか |
| □ | 休憩 | 休憩料金になるか |
| □ | 宿泊 | 宿泊料金になるか |
| □ | 延長 | 料金が増えるか |
| □ | 清掃中 | 部屋状態が変わるか |
| □ | ドアオープン | 音声や表示が出るか |
| □ | 冷蔵庫商品 | 伝票に商品が入るか |

今回やった操作:

```md

```

---

## 5. 🔁 操作後に見る
| チェック | 変化したもの | メモ |
|---|---|---|
| □ | 画面表示 | 変わった / 変わらない |
| □ | 部屋状態 | 例: 空室 → 利用中 |
| □ | 料金 | 円 → 円 |
| □ | 経過時間 | 動いた / 動かない |
| □ | 音声 | 例: 202 ドアオープン |
| □ | 伝票 | 追加された / されない |
| □ | 売上画面 | 反映された / されない |

操作後メモ:

```md

```

---

## 6. 🔌 パソコン入力を確認する
Human Agentは分かる範囲だけでよい。

| チェック | 見るもの | メモ |
|---|---|---|
| □ | 専用キーボードがある | あり / なし |
| □ | ボタン盤がある | あり / なし |
| □ | USBでつながる機器がある | あり / なし |
| □ | LANケーブルでつながる機器がある | あり / なし |
| □ | 丸い端子や古い端子がある | あり / なし |
| □ | 黒い箱や変換器がある | あり / なし |
| □ | 機器に型番が書いてある | 写真を撮る |

型番メモ:

```md

```

---

## 7. 💴 料金システム確認
| チェック | 項目 | メモ |
|---|---|---|
| □ | 休憩料金 | 円 |
| □ | 宿泊料金 | 円 |
| □ | 延長料金 | 円 / 分 |
| □ | 平日 / 休日の違い | あり / なし |
| □ | 時間帯の違い | あり / なし |
| □ | 冷蔵庫料金 | 商品名 / 円 |
| □ | 割引や修正 | あり / なし |
| □ | 売上確定のタイミング | 退室 / 精算 / その他 |

料金メモ:

```md

```

---

## 8. 🚫 絶対に触らない
| チェック | 禁止事項 |
|---|---|
| □ | 配線を抜かない |
| □ | 配線を差し替えない |
| □ | 設定画面を変更しない |
| □ | 既存システムへ書き込まない |
| □ | 業務中に無理な実験をしない |
| □ | 分からない機器を分解しない |

迷ったら:
□ 写真だけ撮る

□ メモだけ残す

□ 触らず止める

---

## 9. 🧠 AI Agentが理解できること
Human Agentが材料を集めると、AI Agentは次を推定できる。

| 集める材料 | AI Agentが推定できること |
|---|---|
| PC裏写真 | 入力経路の候補 |
| キーボード型番 | 専用入力か通常入力か |
| 入力機器、ハブ、変換器の写真 | 信号の入口と変換経路 |
| 操作前後の画面 | EventとState変化 |
| 料金表写真 | Rule、料金計算 |
| 伝票写真 | 売上Event |
| 冷蔵庫料金 | 追加売上Rule |
| 音声メモ | ドア、清掃、警告などのEvent |

---

## 10. 📦 AI Agentへ渡す完成セット
最後に、これだけ揃えばOK。

| チェック | 渡すもの |
|---|---|
| □ | このシートの写真またはPDF |
| □ | PC後ろの写真 |
| □ | 入力機器、ハブ、変換器の写真 |
| □ | キーボード型番の写真 |
| □ | 操作前の画面 |
| □ | 操作後の画面 |
| □ | 料金表 |
| □ | 伝票または売上画面 |
| □ | 操作時の音声メモ |

## 11. 🔁 このミッションで進む循環
このシートからAI Agentが推定する。

- 現場操作が何のイベントになるか
- PCへどの入力形式で入っていそうか
- 部屋状態がどう変わるか
- 料金がどう計算されるか
- 売上イベントとして保存できるか
- 自社OSで最初に作るべき画面とDB
- 不足している情報は何か
- 次のHuman Agent Missionは何か

---

## 12. 🧭 Mission設計ルール
Human Agent Missionは、情報量を最小化するために作るのではない。

目的は、少ないHuman Costで、AI AgentのUnderstanding Gainが最も大きくなるEvidence Setを選ぶこと。

```md
Mission Value = Understanding Gain ÷ Human Cost
```

AI Agentは、Missionを作る時に次の順番で考える。

```md
Goal
↓
Required Evidence Set
↓
Mission Candidate
↓
Human Cost評価
↓
Understanding Gain評価
↓
Mission Value評価
↓
Next Best Mission
↓
Human Agent実行
↓
AI理解度 %
↓
Gap Analysis
↓
次のRequired Evidence Set
```

重要:
過去のRepresentative Pointを固定しない。
202号室は常に正解ではない。
Goalごとに、最も安全で、最も理解が進むRepresentative Pointを選ぶ。

例:

```md
Goal:
信号取得レイヤーを推定したい

Required Evidence Set:
- PC裏写真
- 入力機器写真
- キーボード型番
- 操作前後画面
- 料金表

Representative Point:
業務影響が少なく、操作前後の変化を安全に観測できる部屋
```

## 13. 📈 Mission Value例
| Evidence | Understanding Gain | Human Cost | Mission Value |
|---|---|---|---|
| PC裏全体写真 | 高 | 低 | 高 |
| 料金表写真 | 高 | 低 | 高 |
| デバイスマネージャー確認 | 高 | 中 | 中〜高 |
| COM番号確認 | 中 | 高 | 低〜中 |

AI Agentは、細かい情報を大量に求めるのではなく、Human Agentの負担に対して理解度が最も伸びるMissionを1つ選ぶ。

Mission完了後、AI Agentは次を返す。

```md
理解度:
72%

残りEvidence:
- 全部屋料金表
- 宿泊切替条件
- COMポート番号

これを取得すると:
95%程度まで推定可能
```

数字は目安であり、断定ではない。

---

## 14. 🔬 Human Agent設計 Future Candidate
この節は、JOY Project内のHuman Agent設計仮説である。

新しいPrincipleではない。
Kernel、Principle、AI_CONTEXT、AGENTSには反映しない。

### Future Candidate: Barrier Prediction / Barrier Reduction
目的:
Human Agent Missionを生成する時に、Human Agentがどこで止まるかを先に推定し、心理的摩擦を最小の一文で下げる。

現在の発見:
「写真はきれいじゃなくてOK」「分からなければ写真だけでOK」の価値は、文章そのものではない。
価値があるのは、Human Agentが止まる理由を予測し、その摩擦を短い言葉で取り除く思考アルゴリズムである。

想定Flow:

```md
Mission
↓
Barrier Prediction
Human Agentが止まりそうな理由を推定する
↓
Barrier Reduction
一番短い言葉で摩擦を下げる
↓
Human Agent実行
```

例:

| 想定Barrier | Barrier Reduction |
|---|---|
| 写真をきれいに撮らないといけないと思う | 写真はきれいでなくてOK |
| 分からない機器を触る必要があると思う | 触らず写真だけでOK |
| 正解を書かないといけないと思う | 分からない項目は空欄でOK |
| 作業が長くなりそうに感じる | まず1つだけ操作を見る |

検証対象:
- [ ] JOY PCまわり確認Mission
- [ ] 清掃Mission
- [ ] 料金表収集Mission
- [ ] 経理Evidence収集Mission
- [ ] メール返信確認Mission

昇格条件:
3〜5Projectで、Barrier Prediction / Barrier ReductionによりMission完了率、継続率、心理的負担が改善すること。

現時点ではFuture Candidateとして保存する。

### Future Candidate: Evidence Set Value
目的:
Evidenceを1つずつ評価するのではなく、AI理解度を大きく伸ばす最小の組み合わせとして評価する。

現在の発見:
`キーボード型番`だけではなく、`キーボード全体写真 + 型番写真`の方が、Human Costはほぼ同じでもUnderstanding Gainが高い可能性がある。

Mission設計では、情報量ではなく、Human Costに対するUnderstanding Gainが最大になるEvidence Setを選ぶ。

```md
Evidence Set Value = Understanding Gain ÷ Human Cost
```

例:

| Evidence Set | Understanding Gain | Human Cost | Value |
|---|---|---|---|
| キーボード型番だけ | 中 | 低 | 中 |
| キーボード全体写真 + 型番写真 | 高 | 低 | 高 |
| PC裏全体写真 + 入力機器写真 | 高 | 低 | 高 |
| 操作前画面 + 操作後画面 | 高 | 低 | 高 |
| COM番号確認だけ | 中 | 高 | 低〜中 |

検証対象:
- [ ] JOY PC入力経路
- [ ] 料金表と料金Rule
- [ ] 清掃状態
- [ ] 経理証憑
- [ ] メール対応

昇格条件:
複数Projectで、Evidence単体よりEvidence Setで設計した方が理解度、完了率、継続率が上がること。

現時点ではFuture Candidateとして保存する。

### Future Candidate: Human Agent Cognitive Flow
目的:
Human Agentが自然に行動できる文章やLINEテンプレートを作ることではなく、Human Agentはどの順番、どの粒度、どの余白、どの安心文で情報を受け取ると最も自然に動けるかを研究する。

現在の発見:
良かったのは文章そのものではなく、情報の並ぶ順番と、Human Agentが止まりそうな場所に入っている安心文である可能性がある。

例:

```md
AI Agentから調査依頼
↓
JOY Flow Mission
↓
今日お願いしたいのはこれだけ
↓
ホテルシステム裏側調査
↓
写真を集める
↓
チェックリスト
↓
写真はきれいじゃなくてOK
↓
分からなければ写真だけでOK
↓
禁止事項
↓
こちらで完了
↓
このLINEに写真を送る
```

仮説:
Human Agentは文章を読んでいるのではなく、意味の塊（Chunk）を順番に処理している可能性がある。

現時点のCognitive Flow候補:

```md
Identity
誰から
↓
Context
何のMission
↓
Scope
今日はこれだけ
↓
Meaning
何のため
↓
Action
何をする
↓
Execution List
実際にやるチェック項目
↓
Barrier Reduction
行動前に止まりそうな理由を一文で下げる
行動中に止まりそうな理由を一文で下げる
↓
Risk Control
やってはいけないこと
↓
Completion
何をすれば終わりか
↓
Return Path
どこへ返せばよいか
```

重要:
保存したいのは「写真はきれいじゃなくてOK」という文章ではない。
保存したいのは、MissionごとにHuman Agentが止まりそうな理由をAI Agentが推定し、最小の一文で心理的摩擦を減らす処理である。

追加仮説:
Barrier Reductionは1回だけでは足りない場合がある。
Human Agentが止まる場所が複数あるなら、停止ポイントごとに安心文を複数回配置する必要があるかもしれない。

```md
Barrier Prediction
Human Agentがどこで止まりそうかを予測する
↓
Barrier Reduction
その摩擦を最小の言葉で下げる
↓
Repeated Reassurance
必要な場合は、停止ポイントごとに安心文を複数回配置する
```

Repeated Reassuranceの例:

| 位置 | 想定Barrier | Reassurance |
|---|---|---|
| 行動前 | きれいに撮れないとダメだと思う | 写真はきれいじゃなくてOK |
| 行動中 | 分からない機器で止まる | 分からなければ写真だけでOK |
| 完了前 | 足りないものがあるか不安 | 足りないものはAI Agentがあとで教えます |

認知Chunk候補:
- 余白
- 空行
- 区切り線
- アイコン
- 文章の短さ
- 矢印
- チェックボックス

これらは単なるデザインではなく、Human Agentの認知負荷を下げるために、意味の塊を分ける処理かもしれない。

検証対象:
- [ ] 投資
- [ ] 人体
- [ ] 経理
- [ ] メール返信
- [ ] 清掃
- [ ] 看板調査
- [ ] AI Workspace OS

検証観点:
- Human Agentが最初の一歩を踏み出しやすいか
- 途中で止まる回数が減るか
- Mission完了率が上がるか
- 読み返しが減るか
- 余白、区切り、アイコンが理解を助けているか
- Repeated Reassuranceが重複ではなく停止ポイントごとの摩擦低減として機能するか
- Return Pathが明確だと提出率が上がるか

昇格条件:
3〜5分野で、Cognitive Flowの順番とChunk設計によりHuman Agentの行動開始率、完了率、継続率が改善すること。

現時点ではFuture Candidateとして保存する。

### 境界レビュー
JOY固有:
- PC裏写真
- キーボード型番
- 操作前後画面
- 料金表
- 伝票

Human Agent全般に使える可能性がある上流原理:
- Human Agentが止まる心理的摩擦を先に推定する
- 摩擦を最小の一文で下げる
- 停止ポイントごとに安心文を複数回配置する
- Human Agentが自然に動ける情報順序を設計する
- 意味の塊（Chunk）で認知負荷を下げる
- Return Pathを明確にして提出までつなげる
- Evidence単体ではなくEvidence SetでMission Valueを評価する
- Human Costを増やさずUnderstanding Gainを増やす
- 次のMissionはAI理解度とGap Analysisから作る

弱い部分:
- 現時点ではJOYのLINE文レビューから出た仮説であり、他分野でのEvidenceがない
- Human Agentごとの性格、IT理解度、現場経験によって最適な順番が変わる可能性がある
- 行動開始率や完了率を実測しないと、文章の印象だけで判断してしまう可能性がある
- Repeated Reassuranceは、入れすぎると冗長に見える可能性がある
- 安心文が多すぎると、逆に重要なActionやRisk Controlが埋もれる可能性がある

自己レビュー:
- Layer Leak: なし。JOY Project内のFuture Candidateとして保存している。
- Kernel混入: なし。まだ3〜5Projectで検証されていない。
- Principle化: しない。現時点ではHuman Agent設計の仮説。
- AI_CONTEXT / AGENTS: 変更不要。毎回読む情報ではない。
