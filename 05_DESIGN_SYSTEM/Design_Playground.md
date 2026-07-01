# Design Playground

作成日: 2026-07-02

## 目的

Design Playgroundは、Design Systemを文章で管理するための資料ではない。

実際に見て、触って、比較し、承認するためのDesign Decision Platformである。

目指す状態:

```md
Design Playgroundを開く
↓
Theme / Spacing / Radius / Motionなどを切り替える
↓
LINE / A4 / Dashboard / Web / MobileなどのArtifact Previewを見る
↓
Compare ModeでA案 / B案 / C案を比較する
↓
Userが「これ」と承認する
↓
承認されたDesign TokenをDesign Systemへ戻す
↓
全Artifactへ反映する
```

## 位置付け

```md
Experience
↓
Brand Identity
↓
Design System
↓
Design Playground
↓
Design Decision
↓
Design Token
↓
Presentation
↓
Artifact
```

Design Playgroundは、Designそのものではない。

Designを決める場所である。

## Design Taste Testとの違い

| 項目 | 役割 |
|---|---|
| Design Taste Test | 好み、苦手、方向性を言語化する |
| Design Playground | 実物を見て、触って、承認する |
| Design System | 承認済みのルールとTokenを正本化する |

Taste Testは「好み」。
Playgroundは「実物確認」。
Design Systemは「正本」。

## Playgroundで切り替える項目

### Theme

- Dark
- Light
- Glass
- Minimal

### Spacing

- Compact
- Comfortable
- Relaxed

### Corner Radius

- 8
- 12
- 16
- 20

### Shadow

- None
- Soft
- Medium
- Glass

### Animation Speed

- Fast
- Normal
- Slow

### Animation Style

- Minimal
- Smooth
- Expressive

### Glass Effect

- OFF
- Weak
- Medium
- Strong

### Typography

比較候補:

| Font | 扱い |
|---|---|
| Inter | 基本採用候補 |
| Geist | 比較候補。現代的でミニマル |
| SF系 | Apple的な自然さの比較候補 |
| Playfair Display | 保留。エレガント寄りの比較用 |

判断:
Playfair Displayなどの明朝体、筆記体、エレガント寄りは、最初から採用しない。
Playgroundで比較し、合う場面があるか確認する。

### Icons

基本採用候補:

- lucide-react

方針:
他ライブラリは増やさない。
まずlucide-reactで、太さ、サイズ、余白、ラベルとの組み合わせを確認する。

## Components

Playgroundで最初に確認するComponent:

- Button
- Card
- Dialog
- Mission Card
- Approval Card
- Notification
- Input
- Table
- Dashboard Widget

各Componentは、単体で見るだけではなく、Artifact Preview内でも確認する。

## Artifact Preview

Preview対象:

- LINE
- Human Agent Mission
- A4
- Dashboard
- Web
- Mobile
- Mail
- PDF
- 通知
- Blueprint

重要:
ArtifactごとにDesignの最適解は違う。

例:
- Web / AppではGlassやMotionを使える。
- A4 / PDFでは印刷可読性を優先する。
- LINE / MailではMotionは使わず、余白、改行、短文でリズムを作る。

## Compare Mode

Design Playgroundの中核はCompare Modeである。

目的:
AIが複数案を作り、Userは審査員として選ぶ。

例:

```md
Button A:
radius 8 / compact / shadow none

Button B:
radius 12 / comfortable / shadow soft

Button C:
radius 16 / relaxed / glass
```

Userは「これ」と選ぶだけ。

選択結果はDesign Decisionとして保存し、将来Design Tokenへ反映する。

これはAI Workspace OSの思想と一致する。

```md
AI:
案を作る

Human:
重要な判断と承認だけ行う
```

## Design Token反映の将来構造

将来の理想:

```md
Radius 12 → 16
↓
全画面変更

Spacing 24 → 32
↓
全画面変更

Animation Speed Normal → Fast
↓
全画面変更

Glass Weak → Medium
↓
全画面変更
```

Design Token候補:

| Token | 例 |
|---|---|
| theme | dark / light / glass / minimal |
| spacing | compact / comfortable / relaxed |
| radius | 8 / 12 / 16 / 20 |
| shadow | none / soft / medium / glass |
| glass | off / weak / medium / strong |
| motion.speed | fast / normal / slow |
| motion.style | minimal / smooth / expressive |
| typography.body | Inter / Geist / SF |
| typography.display | Inter / Geist / Playfair Display |
| icon.library | lucide-react |

## Motionとの関係

Animationはライブラリではない。

Design Playgroundでは、Motion Ruleを確認する。

```md
Motion Rule
↓
Library
```

2026-07-02時点の判断:

| 技術 | 扱い |
|---|---|
| Motion / Motion for React | React UIの第一候補。旧Framer Motion系 |
| CSS Transition | Hover / Buttonなど軽いMotionの最軽量候補 |
| View Transition API | Page Transition候補。対応状況とFallback前提 |
| Native Animation | Native Appの標準候補 |

Playgroundでは、ライブラリ名ではなく、次を比較する。

- Fast / Normal / Slow
- Minimal / Smooth / Expressive
- Successの気持ちよさ
- Dialogの自然さ
- Page Transitionの理解しやすさ

## 現在の実装方針

本格アプリ化はまだ行わない。

現時点では、Design System配下に単体で確認できるWeb UIプロトタイプを置く。

保存場所:

```md
05_DESIGN_SYSTEM/playground/index.html
```

役割:
- Design Token切り替えの体験確認
- Component Preview
- Artifact Preview
- Compare Modeの方向確認

注意:
これは正本Tokenではない。
正本化する前の確認UIである。

## 自己レビュー

Layer Leak:
なし。Design System配下のDesign Decision Platformとして扱い、Kernel / Principle / AI_CONTEXT / AGENTSには入れない。

Design Systemとの責務:
自然。PlaygroundはDesign Systemを決めるための確認・承認場所であり、Design System正本そのものではない。

Animationとの責務:
自然。Animation Ruleを見て触って確認する場所であり、ライブラリを固定する場所ではない。

Interactionとの責務:
自然。Button、Dialog、Approvalなど、Humanが触る接点の気持ちよさを確認する。

Presentationとの責務:
自然。ArtifactがHumanにどう届くかを確認する。

Design Taste Testとの違い:
明確。Taste Testは言語化、Playgroundは実物確認。

Design Decision Platformとして自然か:
自然。Humanは案を比較して承認し、AIがToken反映を担当する構造にできる。

## Next Best Action

最初に確認すべきもの:

```md
Mobile Approval Card
```

理由:
AI Workspace OSの最終ビジョンでは、Humanがスマホで承認する体験が最重要だから。

## v2 Review: Design Decision Experience

現行Playgroundは、Design Tokenを確認する最低限の静的HTMLとしては有効。

ただし、Human Agentが専門用語を知らなくても、心地よく直感的にデザインを決める体験としてはまだ弱い。

### 現在の問題点

| 観点 | 問題 |
|---|---|
| 専門用語 | Theme、Spacing、Radius、Shadow、Glass、Typographyなど、Designを知らない人には判断しづらい |
| 操作とPreviewの距離 | 左で設定し、右で全体を見るため、何が変わったか分かりにくい |
| 判断軸 | 「設定値を選ぶ」体験になっており、「どちらが気持ちいいか」で選べない |
| Preview | 全体は見えるが、変更前 / 変更後の比較が弱い |
| Human Agent視点 | 何を判断すればよいかの質問が足りない |
| 心地よさ | Design Decision Platformというより、まだ設定画面に見える |

### 理想のPlayground体験

Design Playground v2は、設定画面ではなくDesign Decision Experienceにする。

理想:

```md
質問
↓
A案 / B案 / C案
↓
横並びPreview
↓
Humanが「好き」を選ぶ
↓
Design Token候補へ反映
↓
次の質問
↓
最後に暫定Design Tokenを表示
```

重要:
HumanはDesign用語を理解しなくてよい。

AIが裏側でTokenへ変換する。

### v2の基本構造

```md
左:
今日のDesign判断
質問
選択肢
Aが好き / Bが好き / どちらも違う

右:
変更前 / 変更後Preview
Artifact Preview
Design Token Candidate
```

### 質問の言葉

専門用語ではなく、体験の言葉で聞く。

| Token | Human向け質問 | 選択肢 |
|---|---|---|
| Spacing | 余白はどちらが気持ちいいですか？ | A: しっかり詰まった印象 / B: ゆったり呼吸する印象 |
| Radius | どちらの丸みが好きですか？ | A: しっかりした印象 / B: やわらかい印象 |
| Motion | この動きは心地いいですか？ | A: 速い / B: ちょうどいい / C: 遅い |
| Glass | どちらが見やすいですか？ | A: 透明感あり / B: はっきり |
| Typography | どちらが読みやすいですか？ | A: 実用的 / B: 少し雰囲気がある |

### Design Decision Log構想

将来は、選択結果をDesign Decision Logへ保存する。

保存するもの:

- 日付
- 質問
- 選んだ案
- 選ばなかった案
- Humanの理由
- 変換されたDesign Token
- 影響Artifact
- 戻す理由

例:

```md
Decision:
Spacingは「ゆったり呼吸する印象」を選択。

Token:
spacing = relaxed

Reason:
Human Agent MissionとMobile Approvalで、読む負担が少なく感じたため。
```

### v2成功条件

- 1画面1判断になっている
- 専門用語を知らなくても選べる
- 変更前 / 変更後が横並びで見える
- Userが「好き / 違う」で判断できる
- 最後に暫定Design Tokenが出る
- Design Taste Testの好みを、実物で検証できる

### 自己レビュー

Layer Leak:
なし。これはDesign System内のPlayground改善であり、Kernel / Principle / AI_CONTEXT / AGENTSには入れない。

Design Systemとの責務:
自然。PlaygroundはDesign System正本を決める前のDecision Platformである。

Design Taste Testとの違い:
明確。Taste Testは好みの言語化。Playground v2は実物を見て選ぶ体験。

Design Decision Platformとして自然か:
v1より自然。Humanは設定値ではなく、体験としての好みを選ぶだけでよい。
