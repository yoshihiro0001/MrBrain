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

## v2.1: Design Token Versioning

Design Playgroundでは、選んだTokenをすぐDesign System本体へ昇格しない。

まず`Design Token Candidate`として保存し、比較、復元、改善できる状態にする。

現在HTML内に表示している`temporary_design_token_candidate`は、次の扱いへ進化させる。

```md
temporary_design_token_candidate
↓
Design Token Candidate
↓
Design Token v0.1
↓
Design Token v0.2
↓
Approved Design Token
↓
Design System本体へ反映
```

### Version管理の目的

Designを一度で確定しない。

触りながら、比較しながら、戻れる状態で育てる。

Version例:

| Version | 状態 | 目的 |
|---|---|---|
| v0.1 | First Candidate | 最初に気持ちいいと感じた方向 |
| v0.2 | Refined Candidate | v0.1の違和感を修正した方向 |
| v0.3 | Artifact Tested | LINE / Mission / Dashboardで確認済み |
| v1.0 | Approved | Design System本体へ反映候補 |

### Candidateに保存するもの

```json
{
  "version": "v0.1",
  "status": "candidate",
  "palette": "Midnight Glass",
  "spacing": "relaxed",
  "radius": 18,
  "motionSpeed": "normal",
  "glass": "medium",
  "typography": "system",
  "keptReason": "Mobile Approvalが一番気持ちよく見えたため",
  "testedArtifacts": ["LINE", "Mission", "Dashboard", "Approval"],
  "decision": "keep"
}
```

### Keep / Discard / Compare

Design Playgroundでは、各候補に対して次の判断を行う。

| Action | 意味 |
|---|---|
| Keep | 気に入ったので候補として残す |
| Discard | 違ったので候補から外す |
| Compare Later | まだ判断しきれないので後で比較する |

重要:
KeepはDesign System本体への昇格ではない。
あくまで候補保存である。

## Color Palette Gallery

Design Playgroundには、Color Palette Galleryを置く。

目的:
色を一つずつ選ぶのではなく、体験ごとのPalette候補を並べ、LINE / Mission / Dashboard / Approval Previewを一括で変化させる。

候補:

| Palette | 印象 | 用途仮説 |
|---|---|---|
| Midnight Glass | 黒、透明感、高級感、集中 | AI Workspace OS / Dashboard / Approval |
| Navy Flow | 落ち着き、信頼、業務感 | 会社運営OS / 経理 / 管理画面 |
| Emerald Signal | 状態変化、完了、前進 | Mission / Success / Signal系UI |
| Warm Minimal | 温かい、やわらかい、疲れにくい | Human Agent Mission / LINE / A4 |
| Hotel Dark | HOTEL JOYらしい夜感、落ち着き | Hotel OS / 予約 / 部屋状態 |

### Palette反映の構想

Paletteを選ぶと、次のPreviewが一括で変化する。

```md
Paletteを選ぶ
↓
LINE Preview
Human Agent Mission Preview
Dashboard Preview
Approval Preview
が同時に変わる
```

確認すること:

- LINEで読みやすいか
- MissionでHuman Agentが止まらないか
- Dashboardで数字が主役になるか
- Approvalで押すのが気持ちいいか
- A4 / PDFへ展開した時に重すぎないか

### Palette Decisionの聞き方

専門用語ではなく、体験の言葉で聞く。

```md
どの空気感が一番しっくり来ますか？

A: 静かで集中できる
B: 信頼できて業務に強い
C: 前へ進む感じがある
D: 温かくて疲れない
E: HOTEL JOYらしい夜の落ち着き
```

## Future Gallery

Color Palette Galleryが有効なら、将来次へ拡張する。

- Icon Style Gallery
- Character Style Gallery
- Illustration Style Gallery

ただし、現時点では新しいDesign System本体へ昇格しない。

まずはPlayground内の候補ギャラリーとして扱う。

### Icon Style Gallery

目的:
lucide-reactを基本にしつつ、太さ、サイズ、余白、ラベルとの相性を比較する。

例:
- Thin
- Regular
- Bold-like
- Filled風

### Character Style Gallery

目的:
Human Agent向けMissionや説明で、キャラクター表現が必要か検証する。

注意:
現時点では保留。
装飾が増えすぎる可能性がある。

### Illustration Style Gallery

目的:
A4、Web、Missionで使う図解や説明イラストの方向性を比較する。

注意:
まずはIcon中心で十分か検証する。

## 上流理論

Design Playgroundの上流理論:

```md
Human Taste
↓
Design Decision Experience
↓
Token化
↓
Artifact反映
↓
Feedback
↓
Token改善
```

意味:
- Human Tasteは、言語化される前の好み、違和感、心地よさ。
- Design Decision Experienceは、それをA/B比較で選べる体験に変換する。
- Token化は、選択を再利用可能なDesign Tokenへ変換する。
- Artifact反映は、LINE / Mission / Dashboard / Approvalへ一括反映する。
- Feedbackは、実際に見て、触って、違和感を集める。
- Token改善は、v0.1からv0.2へ育てる。

この流れにより、Designは一度で決めるものではなく、ExperienceのFeedbackで進化するものとして扱える。

## Design Feedback Inbox

Design Feedback Inboxは、ユーザーがスマホやPCで感じたデザインの違和感を、感覚の言葉のまま受け取る入口である。

これはDesign System本体ではない。
まずDesign Playground内の設計として扱う。

### 役割

- ユーザーの感覚的な違和感を受け取る
- AIが違和感を分類する
- Design Token候補へ変換する
- Preview改善案へ変換する
- Codexへの修正指示文へ変換する
- Playgroundへ反映する
- Keep / Discard / Compareで評価する
- Design Token Candidateを更新する

### 受け取るFeedback例

ユーザーは専門用語で書かなくてよい。

例:

- 字間が詰まっている
- もう少し心地よく
- 色パターンを増やしたい
- スマホで見たい
- 丸すぎる
- 余白が気持ちよくない
- アニメーションが少し邪魔
- もっとはっきり見たい
- もう少し高級感がほしい
- LINEだと長く感じる

重要:
Feedbackは、正しいDesign用語ではなくHuman Tasteの生データとして扱う。

### Feedback分類

AIはFeedbackを次のカテゴリへ分類する。

| Category | 見るもの |
|---|---|
| Typography | 文字、字間、行間、読みやすさ |
| Spacing | 余白、詰まり、呼吸感 |
| Color | 色、コントラスト、Palette |
| Radius | 丸み、硬さ、やわらかさ |
| Glass | 透明感、見やすさ、背景の重さ |
| Motion | 動き、速さ、邪魔さ、気持ちよさ |
| Interaction | 押しやすさ、反応、承認体験 |
| Layout | 配置、視線、情報の順番 |
| Component | Button、Card、Dialog、Tableなど |
| Artifact | LINE、A4、Dashboard、Mailなど |
| Mobile | スマホでの読みやすさ、押しやすさ |
| Accessibility | 文字サイズ、コントラスト、疲れにくさ |

### 変換Flow

```md
Human Feedback
↓
AI分類
↓
Design Token候補
↓
Preview改善案
↓
Codex指示文
↓
Playground反映
↓
Keep / Discard / Compare
↓
Design Token更新
```

### Feedback Item Template

```md
Feedback ID:

Raw feedback:

Target artifact:

Category:

Intent:

Affected token:

Proposed change:

Priority:

Status:

Generated Codex instruction:
```

記入例:

```md
Feedback ID:
DF-0001

Raw feedback:
スマホで見ると少し詰まっている。

Target artifact:
Mobile Approval

Category:
Spacing / Mobile

Intent:
承認画面を疲れにくく、押しやすくしたい。

Affected token:
spacing, button height, card padding

Proposed change:
spacingをcomfortableからrelaxedへ寄せ、Buttonの高さを少し上げる。

Priority:
High

Status:
Candidate

Generated Codex instruction:
Design Playground v2のMobile Approval Previewで、spacing relaxed案を追加し、現行案とA/B比較できるようにしてください。
```

### スマホ運用

将来的には、スマホから一言でFeedbackを入れられるようにする。

例:

```md
この画面、少し詰まって見える
```

AIはこれを受け取り、次へ変換する。

```md
Category:
Spacing / Mobile / Layout

Intent:
スマホでの読みやすさと余白を改善したい

Codex instruction:
Mobile PreviewのSpacing比較を追加してください
```

将来像:

```md
Design Feedback Inbox
↓
AI分類
↓
Codex修正案
↓
Playground反映
↓
User承認
↓
Design Token Candidate更新
```

これはApproval Inbox / Mission Inboxと同じ思想である。
ただし、現時点ではMarkdown設計で十分。

### Playgroundとの関係

| 項目 | 役割 |
|---|---|
| Design Playground | Designを見て、触って、比較する場所 |
| Design Feedback Inbox | 違和感を入れる場所 |
| Design Token Versioning | 反映結果を保存、比較、復元する場所 |
| Design System本体 | 承認済みTokenとRuleの正本 |

Design Playgroundは見る場所。
Design Feedback Inboxは違和感を入れる場所。
Design Token Versioningは反映結果を保存する場所。

### 今は作りすぎない

現時点では、`05_DESIGN_SYSTEM/Design_Feedback_Inbox.md`を新規作成しない。

理由:
- まだFeedback実績が少ない
- Inboxとして独立させる前に、Playground内で分類と変換Flowを検証したい
- ファイルを増やすより、まず違和感 → Codex指示化が自然に回るか確認する

将来、Feedbackが増えた場合は、新規ファイル化を検討する。

候補:

```md
05_DESIGN_SYSTEM/Design_Feedback_Inbox.md
```

## v2.1自己レビュー

Layer Leak:
なし。Design Playground内の保存、比較、復元の構想であり、Design System本体へはまだ昇格しない。

Design Systemとの責務:
自然。Playgroundは候補を育てる場所。Design System本体は承認済みTokenの正本。

Color Palette Galleryの責務:
自然。色を個別指定ではなくExperience単位で比較するための候補ギャラリー。

Versioningの責務:
自然。Git commitとは別に、Design Candidateの意味ある変化を追跡する。

将来拡張:
Icon / Character / Illustrationはまだ保留。Color Palette Galleryで効果を確認してから広げる。

Design Feedback Inboxとの違い:
Playgroundは見て決める場所。Feedback Inboxは違和感を受け取る場所。Versioningは反映結果を候補として保存する場所。

Design System本体へ昇格する条件:
複数回のFeedbackが集まり、カテゴリ分類、Token変換、Codex指示化、Preview反映、Keep / Discard / Compareの流れが3〜5回自然に成立すること。
