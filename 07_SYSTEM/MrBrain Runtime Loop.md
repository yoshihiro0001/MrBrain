# MrBrain Runtime Loop

## 位置づけ
MrBrain Runtime Loopは、AI専用の手順ではない。

人・AI・Agent・システムを問わず、あらゆる判断・設計・実行・学習を循環させる普遍的な実行原理である。

MrBrainを情報保管庫ではなく、判断、設計、実行、記録、学習が循環するOSとして動かすための正本にする。

## 4層設計
MrBrainは、Kernel、Router、Library、Projectの4層で扱う。

```md
Kernel
↓
Router
↓
Library
↓
Project
```

この4層の実行入口は `07_SYSTEM/MrBrain Kernel Router.md` とする。

Runtime Loopは詳細正本であり、毎回全文を読む対象ではない。

### Kernel
毎回使う最小OS。

```md
憲法
安全
Goal
Success Condition
Source First
Hypothesis
Minimal Information
Route
Output
Learn
```

### Router
Routerが中心である。

Routerは、依頼を分類し、必要なLibraryとProjectだけを読む。
AIは全ファイルを読まない。

### Library
必要時だけ読む思考、設計、判断の正本。

例:
- 接続理論
- エネルギー循環OS
- Blueprint Engine
- Human Communication OS
- Blueprint Reviewer
- セキュリティルール

### Project
JOY、経理、投資、SNS、人体など、対象別の現実情報、Blueprint、対応表、ログ。

## Boot Sequenceとの関係
Boot Sequenceは、AIがMrBrainを使い始める時の下位概念である。

Runtime Loopは、起動後も毎回の相談、設計、実装、記録、学習で回り続ける実行原理である。

```md
Boot Sequence
↓
Runtime Loop
↓
Operation Log
↓
Evolution Loop
↓
次のRuntime Loop
```

## 7 Phase

### 1. Anchor
憲法・安全ルール・判断基準に接続する。

見るもの:
- 最上位憲法
- 安全ルール
- 判断基準
- 削除、移動、外部公開のリスク

主な参照:
- `07_SYSTEM/MrBrain Kernel Router.md`
- `07_SYSTEM/エネルギー循環OS憲法.md`
- `07_SYSTEM/セキュリティルール.md`
- `02_PRINCIPLES/判断基準.md`

### 2. Sense
依頼内容、現在地、滞り、目的を読む。

見るもの:
- ユーザーが何を求めているか
- どこで循環が止まっているか
- 今やるべきことか
- 現在の優先順位

主な参照:
- `07_SYSTEM/AI_CONTEXT.md`
- `00_HOME/TASKS.md`
- `00_HOME/HOME.md`

## Thinking Engine
Thinking Engineは、SenseとRouteの間に必ず通る思考処理である。

MrBrainは、質問を受けたらすぐBlueprintを作らない。

まず、人間の思考を整理し、本質を抽出し、最小情報で最短距離の答えを探す。

Blueprintは思考の出発点ではない。

必要な場合の設計成果物である。

ただし、Blueprintで終わらない。

重要な構造は、交換可能なComponentにし、自然に循環するFlowへ接続し、他分野でも再利用できるかEvolutionで確認する。

この目的は、価値の低い判断を圧縮し、価値の高い思考にエネルギーを集中させることである。

### Thinking Flow
```md
質問
↓
対象を1文で定義する
↓
本当のGoalを1文で定義する
↓
現在もっとも有力なHypothesisを1〜3個出す
↓
Success Conditionを1文で定義する
↓
Source First Checkを行う
↓
対象世界を1文で定義する
↓
その世界を動かしているルールを1文で定義する
↓
目的を1文で定義する
↓
本質を1文で定義する
↓
Root Structureを1文で定義する
↓
Representative Pointを1文で定義する
↓
Leverage Pointを1文で定義する
↓
最小構造へ分解する
↓
今分からない部品を列挙する
↓
Hypothesisを最短で検証・否定できる情報を特定する
↓
Success Conditionを満たすMinimal Information Setを提示する
↓
これだけ分かれば7〜8割推測できる最小確認情報を提示する
↓
最短ルートを提案する
↓
Blueprintが必要なら初めてBlueprintを作る
↓
Component化できるか確認する
↓
価値の低い判断を圧縮できるか確認する
↓
Flowとして自然に循環するか確認する
↓
他分野へ再利用できるか確認する
↓
Energy Cost Checkを行う
```

### 最重要原則
Blueprintを増やすことが目的ではない。

目的は、人間が考える量を減らし、最短でゴールへ到達できるようにすることである。

### 毎回確認する問い
- 対象は何か
- ユーザーの本当のGoalは何か
- 現在もっとも有力なHypothesisは何か
- そのHypothesisを最短で検証・否定できる情報は何か
- 何が分かれば終わりか、Success Conditionは何か
- 下流の承認、集計、税務の前に、最初の源流データはどこで発生するか
- その源流がないと、後工程が成立しないものは何か
- Success Conditionを満たすためのMinimal Information Setは何か
- これは何という世界か
- その世界は何で動いているか
- その世界のルールは何か
- この質問の本質は何か
- この対象を成立させている一番上流で、最も変えにくい構造は何か
- そのRoot Structure全体を代表する一点はどこか
- そのRoot Structureを、最も効率よく観測・介入できる場所はどこか
- 一番シンプルな構造は何か
- 本当に必要な情報は何か
- この情報だけで何％まで推測できるか
- 不足分だけ追加確認するなら何か
- どこが最大のボトルネックか
- 一番少ない行動で前へ進める方法は何か
- Blueprintは本当に必要か
- この構造は交換可能なComponentにできるか
- 一度理解した構造を、二度と考えなくてよい形へ保存できるか
- 価値の低い判断を圧縮できるか
- 価値の高い思考にエネルギーを戻せるか
- 他分野でも再利用できるか
- ユーザーが読む量、考える量、確認する量、動く量をさらに減らせないか

### World Modeling
World Modelingは、対象を見る前に、その対象が属している世界を理解する思考である。

ユーザーは、分野名から考え始めない。

まず、次の問いから始める。

```md
これは何という世界か
↓
この世界は何で動いているか
↓
この世界のルールは何か
↓
そのルールのRoot Structureは何か
```

服、ホテル、投資、人体、税務、恋愛、システム開発は、最初の分類ではない。

先に、その対象世界を成立させているルールを見る。

例:
- 服の世界: 印象、シルエット、素材、色、体型、場面のルールで動く
- ホテルシステムの世界: 現場操作、電気信号、入力機器、イベント、料金、画面表示のルールで動く
- 投資の世界: 価値創出、利益構造、市場期待、経営者、資本配分のルールで動く
- 人体の世界: エネルギー、神経、血流、炎症、ホルモン、細胞修復のルールで動く
- 税務の世界: 取引、証憑、支払い、勘定科目、税区分、申告項目のルールで動く

Thinking Engineの本当の開始点は、Root Structureではない。

まず対象世界をモデル化し、その世界のルールを見つけ、その後にRoot Structure、Leverage Pointへ進む。

### Goal / Hypothesis / Success Condition
AIは、ユーザーの言葉をそのまま目的として扱わない。

まず、本当のGoalを推定する。

次に、現時点でもっとも有力なHypothesisを1〜3個出す。

Hypothesisは、情報収集の前に置く。

情報収集は、網羅ではなく仮説検証である。

次に、そのGoalが達成されたと言えるSuccess Conditionを定義する。

```md
ユーザーの言葉
↓
本当のGoal
↓
Hypothesis
↓
Success Condition
↓
Hypothesisを検証・否定できる情報
↓
Minimal Information Set
↓
Maximum Inference
↓
不足分だけ確認
```

例:
- 「信号を知りたい」
  - Goal: 自社OSが既存ホテルシステムのイベントを受け取れるか判断する
  - Hypothesis:
    1. 既存PCはUSB HIDまたはキーボード相当の入力を受けている
    2. USB HIDでなければCOM / シリアル入力の可能性が高い
    3. それでもなければLAN、ログ、画面表示の順に確認する
  - Success Condition: 既存PCへ入っている入力経路と、自社OSが読める可能性の高い観測点が分かる
  - Minimal Information Set: PC背面写真、キーボード型番、入力機器型番、デバイスマネージャー、既存ソフト画面

AIは、情報をたくさん集めるのではなく、現在もっとも有力な仮説を最短で検証・否定できる最小情報集合を見つけることを優先する。

仮説が外れた場合だけ、次の仮説へ進む。

回答では、必要に応じて次の形で返す。

```md
Goal:
Hypothesis:
Success Condition:
Minimal Information Set:
この情報だけで推論できること:
仮説が外れた場合の次候補:
不足分だけ確認すること:
次の最短ルート:
```

### Source First Check
Source First Checkは、下流の承認、集計、税務、出力へ進む前に、最初の源流データがどこで発生するかを確認する工程である。

AIは、確認画面や月次集計を先に設計しない。

まず、循環が止まっている最初の源流を見る。

```md
源流
↓
イベント化
↓
状態変化
↓
金額発生
↓
DB保存
↓
承認
↓
月次集計
↓
税務出力
```

例:
- JOYでは、売上承認の前に、部屋操作、信号、部屋状態、料金計算、売上発生がある
- 経理では、月次集計の前に、取引、証憑、支払い、明細がある
- 人体では、症状判断の前に、神経、血流、炎症、ホルモン、細胞エネルギーなどの源流がある

下流の画面が正しくても、源流が取れていなければ循環は成立しない。

したがって、AIは次を必ず確認する。

```md
このデータはどこで最初に発生するか？
その源流を受け取れているか？
源流がない場合、下流設計に入ってよいか？
```

### Root Structure Thinking
Root Structure Thinking（根構造思考）は、現象ではなく、その現象を成立させている一番上流で、最も変えにくい構造を先に探す思考である。

ただし、Root Structureを見つけること自体が目的ではない。

本当の目的は、Root Structureから、最も効率よく観測・介入できる場所であるLeverage Pointを見つけることである。

AIは、複雑な相談を受けたら、固定の答えを当てはめない。

まず対象を決め、その対象ごとのRoot Structureを探す。

```md
対象
↓
World Model
↓
World Rules
↓
Root Structure
↓
Representative Point
↓
Leverage Point
↓
最小構造
↓
Minimal Information
↓
Maximum Inference
↓
Minimal Verification
↓
必要ならBlueprint
↓
Component
↓
Flow
↓
Evolution
```

重要なのは、「上流」は毎回同じではないこと。

- ホテルシステムなら、Root Structureは電気信号や入力経路になることがある
- 人体なら、目的に応じて神経、血流、ホルモン、細胞エネルギーなどになる
- 投資なら、価値を生み出す構造、利益構造、需要、経営者の意思決定などになる
- 税務なら、取引、証憑、支払い、消費税区分、申告入力項目などになる
- 人間関係なら、欲求、理解、安心、信頼、行動の流れなどになる

写真、型番、スクショ、画面表示は原理ではない。

それらは、Root Structure、Representative Point、Leverage Pointを特定するためのMinimal Informationである。

### Representative Point
Representative Point（代表点）は、Root Structure全体を代表して読む一点である。

Root Structureを見つけた後、全部を見ようとしない。

その全体を最もよく代表する一点を探す。

```md
Root Structure
↓
全部を見る
↓
情報が多すぎる
```

ではなく、

```md
Root Structure
↓
Representative Point
↓
少ない情報で全体を読む
```

例:
- ホテルシステム: 電気信号全体ではなく、既存PCへ入る入力、入力機器、画面表示、ログなどを代表点として見る
- 人体: 全身を全部見るのではなく、炎症、血流、神経、ホルモン、検査値など、状態を代表する点を見る
- 服: 全ワードローブではなく、制服一着、スラックス、シャツ、靴など、印象と運用を代表する点を見る
- 投資: 会社全体ではなく、利益、社長、主力商品、顧客、採用など、企業価値を代表する点を見る

Representative Pointがあるから、少ない写真、型番、スクショ、数値、発言から7〜8割推論できる。

### Leverage Point
Leverage Pointは、Root Structureを見つけた後に探す、最小の観測点・介入点である。

問いは次の通り。

```md
Root Structureは何か
↓
どこを見れば一番効率よく分かるか
↓
どこなら一番簡単に取得できるか
↓
どこに介入すれば最小コストで循環が動くか
```

例:
- ホテルシステム: 電気信号そのものではなく、既存PCへ入った入力形式、画面表示、ログ、帳票、入力機器のどこを観測すれば最も効率がよいかを見る
- 投資: 会社の利益構造を見たうえで、社長発言、採用、IR、展示会、取引先、補助金など、未来を読む情報量が多い観測点を探す
- 人体: 症状名ではなく、神経、血流、炎症、ホルモン、細胞エネルギーのどこを測れば情報量が多いかを見る
- 税務: 申告書だけでなく、取引、証憑、支払い、勘定科目、消費税区分のどこを整えれば後工程が最も楽になるかを見る

### ユーザー思考特性
ユーザーは、複雑な現象を対象世界として捉え、その世界のルールを見つけてから、Root Structure、Leverage Point、最小構造へ分解して考える傾向がある。

```md
Signal
↓
Event
↓
Logic
↓
Database
↓
UI
```

または、現場の言葉では次のように捉える。

```md
信号
↓
入力
↓
変換
↓
出力
↓
循環
```

MrBrainは、この思考構造を優先して、本質、最小構造、不足情報、最短ルートを先に出す。

情報収集では、全部集めようとしない。

Root StructureとLeverage Pointを特定するために、最小限必要な情報だけを先に集める。

その情報だけで7〜8割推論し、不足分だけ確認する。

### Component / Flow / Evolution
ユーザーは、Blueprintを作ること自体を目的にしていない。

本当に求めているのは、一度理解した構造を永続的に再利用できる形にすることである。

```md
現象
↓
Root Structure
↓
Leverage Point
↓
Minimal Information
↓
Maximum Inference
↓
Blueprint
↓
Component
↓
Flow
↓
Evolution
```

#### Component
Componentは、交換可能な部品である。

一度理解した構造を、特定の案件だけで終わらせず、他の場所でも使える部品にする。

例:
- ホテル信号を `Event` として扱えば、ドア、清掃、冷蔵庫、売上、部屋状態を同じ仕組みで扱える
- 経理の取引を `Transaction` として扱えば、売上、支出、カード明細、銀行入出金を同じ仕組みで扱える
- 投資の会社情報を `Company Card` として扱えば、銘柄ごとの比較、危険サイン、発表前の匂いを同じ仕組みで扱える

#### Flow
Flowは、Componentが自然に循環する仕組みである。

部品を作って終わりにしない。

入力、変換、保存、表示、確認、学習、再利用まで流れるかを見る。

#### Evolution
Evolutionは、その構造が他分野でも再利用できるかを確認する工程である。

```md
ホテルで使えた構造
↓
経理にも使えるか
↓
投資にも使えるか
↓
人体にも使えるか
↓
MrBrain自身にも使えるか
```

Evolution Lawに従い、1回の発見をすぐ原理化しない。

ただし、3分野以上で再利用され、OS全体をよりシンプルにできる場合は、Principle Candidateとして扱う。

### Decision Compression
Decision Compression（判断圧縮）は、価値の低い判断を圧縮し、価値の高い思考にエネルギーを集中させる考え方である。

ただし、Decision Compressionは最上位概念ではない。

標準化、部品化、OS化、判断圧縮は、すべて循環を止める摩擦を消すための実装パターンである。

ユーザーは標準化を目的としているのではない。

未来の自分や他者が、同じ問題を二度と考えなくてよい構造を作ることを目的としている。

その結果として、標準化、部品化、OS化、判断圧縮が生まれる。

```md
循環
↓
摩擦発見
↓
Root Structure
↓
Representative Point
↓
Leverage Point
↓
最適解
↓
標準化
↓
部品化
↓
OS化
↓
判断圧縮
↓
循環改善
```

目的は、すべての判断をなくすことではない。

毎回考える価値が低いものを構造化し、標準装備、テンプレート、Component、Flowとして固定する。

その結果、ユーザーは本質判断、創造、探索、人との関係、新しい設計など、価値の高い思考にエネルギーを使える。

例:
- 服: 最高に合う制服セットを見つけ、予備まで持つことで、毎日の服選びの判断を圧縮する
- 経理: 取引、証憑、承認、集計、申告までのFlowを作り、毎回の確認漏れや転記判断を圧縮する
- ホテル運営: 現場イベントをComponent化し、部屋状態、清掃、売上、冷蔵庫を同じFlowで扱う
- 投資: 勝つ構造、危険サイン、発表前の匂いを見る基準を作り、毎日のニュース判断を圧縮する
- 人体: 症状ごとに迷うのではなく、循環構造とLeverage Pointを見て、確認すべき場所を圧縮する

注意:
変化そのものが価値になる領域では、判断を完全に圧縮しない。

新しいデザインの発想、人との関係、新規事業の探索などは、毎回考えること自体に価値がある。

したがって、圧縮するのは価値の低い反復判断であり、価値の高い探索や創造は残す。

### Energy Cost Check
Energy Cost Checkは、Thinking Engineの最後に行う確認である。

ユーザーが求めているのは、情報量の多い正解ではない。

最も少ないエネルギーで、最も大きな循環改善が得られる答えである。

回答前に、必ず次を確認する。

```md
この回答で、
ユーザーが読む量
考える量
確認する量
動く量
をさらに減らせないか？
```

減らせるなら、より少ない行動で同じSuccess Conditionへ届く構造を優先する。

ただし、安全、税務、契約、個人情報に関わる確認は、エネルギー削減を理由に省略しない。

### 3. Route
必要な正本、Agent、Blueprint、Reviewの有無を選ぶ。

全ファイルを読まない。

必要な部品だけ読む。

Thinking Engineで、Blueprintが必要と判断された場合だけBlueprint Engineへ進む。

選ぶもの:
- 正本ファイル
- Agent
- Blueprint Engineが必要か
- Blueprint Reviewが必要か
- Operation Logへ戻す必要があるか

主な参照:
- `07_SYSTEM/MrBrain Kernel Router.md`
- `07_AGENTS/README.md`
- `04_PROJECTS/PROJECTS.md`
- `03_BUSINESS/BUSINESS_INDEX.md`

### 4. Shape
返信、記録、Blueprint、設計案、実装案などに変換する。

依頼内容を、そのまま処理しない。

必要な形へ変換する。

出力例:
- 返信文
- 記録用Markdown
- Blueprint
- 設計レビュー
- 実装指示
- 調査計画
- 次の1手

主な参照:
- `02_PRINCIPLES/Blueprint Engine.md`
- `07_AGENTS/Blueprint Agent.md`
- `02_PRINCIPLES/Human Communication OS.md`
- `07_AGENTS/Communication Agent.md`

### 5. Verify
安全性、接続漏れ、循環停止、実装前Reviewを確認する。

実行前に止まる場所である。

確認すること:
- 個人情報、税務情報、契約情報は安全か
- 接続漏れはないか
- 循環が止まる場所はないか
- 原本と正本は分かれているか
- テスト方法と戻し方はあるか
- Blueprint Reviewが必要か

主な参照:
- `07_AGENTS/Blueprint Reviewer.md`
- `07_SYSTEM/Blueprint v2 Template.md`
- `07_SYSTEM/セキュリティルール.md`

### 6. Act
必要最小限で実行する。

コード、Markdown編集、返信文作成、整理、調査、記録などはここで行う。

原則:
- コードは最後
- 最小変更
- 削除、移動は確認後
- 原本を守る
- 変更理由を残す

### 7. Learn
結果をOperation Log、Decision Log、TASKS、AI_CONTEXTへ戻す。

実行して終わりにしない。

学びをMrBrainへ戻し、次のRuntime Loopを良くする。

戻す場所:
- 実行結果: `07_SYSTEM/Operation Log.md`
- 重要判断: `07_SYSTEM/DECISION_LOG.md`
- 次の作業: `00_HOME/TASKS.md`
- 毎回必要な短い背景: `07_SYSTEM/AI_CONTEXT.md`
- 自動化候補: `07_SYSTEM/Automation Backlog.md`

## Evolution Law
新しい原理は、より多くの原理を増やすためではなく、より少ない原理で、より多くの現象を説明できる場合にだけ昇格する。

新しい発見は記録してよい。

ただし、思いつきだけで `02_PRINCIPLES` や `07_SYSTEM` の正本原理へ昇格しない。

新しい原理として正本化を検討するには、次の4条件をすべて満たす必要がある。

1. 少なくとも3つ以上の異なる分野で再利用されたこと
   - 例: ホテル、投資、人体、経理、SNS、AI開発、人間関係
2. 長期的にも価値があること
3. 既存の原理では十分に説明できないこと
4. OS全体をよりシンプルにできること
   - 新しい原理を増やすより、既存原理を統合・圧縮できることを優先する

新しい原理を追加する前に、既存の原理を拡張・統合して説明できないかを必ず検討する。

目的は、原理やファイルを増やすことではない。

より少ない原理で、より多くの現象を説明できるOSへ進化させることである。

### 原理の成熟段階
新しい気づきは、すぐにCore Principleへ昇格しない。

次の4段階で扱う。

| 段階 | 意味 | 置き場所 |
|---|---|---|
| Observation | 1回の気づき、違和感、発見 | Operation Log、日次ログ、対象プロジェクト |
| Pattern | 複数回出た傾向 | Operation Log、関連プロジェクト、判断ログ |
| Principle Candidate | 3分野以上で再利用された原理候補 | 対象ファイル、DECISION_LOG、必要ならBlueprint |
| Core Principle | 4条件を満たして正本化された原理 | `02_PRINCIPLES` または `07_SYSTEM` |

### 例外
安全、税務、契約、個人情報、秘密情報に関するルールは、原理ではなくガードレールである。

危険がある場合は、3分野での確認を待たず、`07_SYSTEM/セキュリティルール.md`、`AGENTS.md`、関連ファイルへ即時反映してよい。

## 読み込み階層
トークン消費を最小化するため、毎回すべてを読まない。

```md
Kernel
↓
Router
↓
Library
↓
Project
```

### Kernel
必ず読む最小ルール。

- `07_SYSTEM/MrBrain Kernel Router.md`
- `07_SYSTEM/AI_CONTEXT.md`
- `00_HOME/TASKS.md`

### Router
依頼内容から、必要なLibraryとProjectを選ぶ。

Routerは、読む量を増やすためではなく、読む量を減らすために使う。

### Library
依頼に関係する正本だけ読む。

例:
- 設計: `02_PRINCIPLES/Blueprint Engine.md`
- 返信: `02_PRINCIPLES/Human Communication OS.md`
- 接続理論: `02_PRINCIPLES/接続理論.md`
- 投資: `04_PROJECTS/株スクリーニング/投資家OS構想.md`

### Project
実際に確認、編集、レビューする対象ファイル。

例:
- JOY信号: `04_PROJECTS/ホテルシステム/JOY_信号_PC処理対応Blueprint.md`
- 経理: `04_PROJECTS/経理アプリ/会社運営OS_ゼロベース再設計レビュー.md`
- スプレッドシート: `04_PROJECTS/スプレッドシート整理/SPREADSHEET_INDEX.md`

## Blueprint Engineとの関係
Blueprint Engineは、Runtime LoopのRoute / Shapeで使う設計エンジンである。

Blueprintを作る場合は、次の流れになる。

```md
Anchor
↓
Sense
↓
Thinking Engine
↓
Route
↓
Blueprint Engine
↓
Shape
↓
Verify
↓
Act
↓
Learn
```

## Blueprint Reviewとの関係
Blueprint Reviewは、Runtime LoopのVerifyで使う。

実装、外部公開、個人情報、税務、契約、長期運用に関わる場合は、Actの前に必ず確認する。

## 適用例

### ホテル
```md
Anchor: 接客と安全の原則に接続
Sense: 問い合わせ内容とお客様の感情を読む
Route: Communication Agentを選ぶ
Shape: 返信文へ変換
Verify: 安心、事実確認、個人情報を確認
Act: 返信
Learn: テンプレート改善へ戻す
```

### 経理
```md
Anchor: 安全、税務、正本ルールに接続
Sense: 経理の滞りを読む
Route: Blueprint Agentを選ぶ
Shape: 入力、確認、保存の設計へ変換
Verify: 税務情報、原本、戻し方を確認
Act: 最小運用または実装
Learn: Operation LogとAutomation Backlogへ戻す
```

### 投資
```md
Anchor: 構造を見る原則に接続
Sense: 会社情報と違和感を読む
Route: 投資家OS構想を選ぶ
Shape: 会社カードや危険サインへ変換
Verify: 未確認情報や過大評価を確認
Act: 判断補助を作る
Learn: 仮説と結果を戻す
```

### 人体
```md
Anchor: 接続理論と安全原則に接続
Sense: 症状や違和感を読む
Route: 接続理論を選ぶ
Shape: 上流、流れ、最小介入の仮説へ変換
Verify: 医療断定を避け、専門家確認を前提にする
Act: 記録、観察、相談準備
Learn: 健康ログへ戻す
```

### SNS
```md
Anchor: 外部公開と判断原理に接続
Sense: 伝えたい原理と対象を読む
Route: SNS Posting Engineを選ぶ
Shape: 投稿案へ変換
Verify: 誤解、個人情報、未確認情報を確認
Act: 投稿または下書き
Learn: 反応をMrBrainへ戻す
```

## Agentが増えても破綻しないルール
Agentが増えても、全Agentを読まない。

Routeで必要なAgentだけを選ぶ。

Agentを増やす前に、既存Agentの役割で足りないか確認する。

## 重要
Runtime Loopは、作業を重くするためのものではない。

考える順番を固定し、読む量を減らし、必要な部品だけ接続し、結果を次の循環へ戻すためのOSである。
