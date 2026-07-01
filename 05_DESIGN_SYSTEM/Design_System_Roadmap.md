# Design System Roadmap

作成日: 2026-07-02

## 目的

AI Workspace OSが生成する全成果物を、同じ世界観で出力できるDesign Systemへ育てる。

最終目的:

```md
一つのDesign変更
↓
全Artifactへ一貫して反映
```

対象:
- LINE
- A4指示書
- Dashboard
- Web
- Mobile App
- PDF
- メール
- 通知
- Blueprint
- Human Agent Mission

## 基本方針

最初から全ファイルを作らない。

まずはDesign Systemの正本を小さく作り、実際のArtifact生成で必要になったものだけ分割する。

```md
Observation
↓
Pattern
↓
Token
↓
Template
↓
Design System
```

## Phase 0: 現状整理

目的:
既存のデザイン引き継ぎ資料を、Design System化の土台として整理する。

やること:
- `デザイン引き継ぎファイル.md`をDesign Handover Sourceとして扱う
- `UI_DESIGN_GUIDELINES.md`をUI Rule Sourceとして扱う
- `01_ME/好きなデザイン.md`をUser Preference Sourceとして扱う
- 重複、不足、統合候補を洗い出す

成果物:
- `Design_System_Architecture_Review.md`
- `Design_System_Roadmap.md`

Status:
完了。

## Phase 1: Design Kernel作成

目的:
AIが最初に読むDesign Systemの入口を作る。

作る候補:

```md
05_DESIGN_SYSTEM/00_Design_System.md
05_DESIGN_SYSTEM/README.md
```

`00_Design_System.md`に入れるもの:
- Brand Identity要約
- Design Philosophy要約
- Token参照
- Template選択ルール
- Presentation Check
- 禁止事項

この段階では、全Templateを作らない。

完了条件:
AIが`00_Design_System.md`だけ読んで、LINE / A4 / Dashboardの方向性を80%判断できる。

## Phase 2: Design Token作成

目的:
Designを一箇所変更すれば、全成果物へ反映できる土台を作る。

作る候補:

```md
05_DESIGN_SYSTEM/02_Design_Tokens.md
```

Token候補:
- Color
- Typography
- Spacing
- Radius
- Shadow / Glass
- Icon
- Motion
- Status

注意:
Templateに直接スタイルを書きすぎない。
TemplateはTokenを参照する。

完了条件:
黒背景、ガラス、主役情報、余白、状態色、文字階層をTokenとして説明できる。

## Phase 3: Artifact Template最小化

目的:
成果物ごとの出力のブレを減らす。

最初に作るTemplate候補:

```md
05_DESIGN_SYSTEM/03_Artifact_Templates.md
```

最初に扱うArtifact:
- LINE
- A4指示書
- Dashboard
- Human Agent Mission

理由:
HOTEL JOYの実案件で最も早く使う可能性が高い。

Template方針:
- 完成形を固定しすぎない
- Section順、情報量、禁止事項、チェック項目を定義する
- 色や余白はTokenを参照する

完了条件:
同じMissionを、LINE / A4 / Dashboard向けに一貫した世界観で変換できる。

## Phase 4: Presentation Layer接続

目的:
AI Workspace OSのArtifact生成後、Design Systemを通してPresentationを整える。

接続Flow:

```md
Goal
↓
AI Workspace OS
↓
Artifact生成
↓
Presentation Layer
↓
Design System
↓
Human
```

やること:
- Artifact種別を判定する
- 必要Templateを選ぶ
- Design Tokenを適用する
- Humanが迷わず動けるか確認する

完了条件:
AIが成果物を出す時に、Design Systemを参照した形式で出せる。

## Phase 5: 実案件検証

検証対象:

| Project | Artifact | 検証すること |
|---|---|---|
| HOTEL JOY | Human Agent Mission | 現場で迷わず動けるか |
| HOTEL JOY | A4指示書 | 印刷して使えるか |
| HOTEL JOY | LINE文 | スマホで読んで動けるか |
| 会社運営OS | Dashboard | 主役情報が見やすいか |
| 経理 | 確認表 / PDF | 税理士や人間が確認しやすいか |

完了条件:
3つ以上のArtifactで、Design System参照によって品質が安定する。

## Phase 6: ファイル分割

次の条件を満たしたら、細かいファイルへ分割する。

分割条件:
- `02_Design_Tokens.md`が長くなりすぎた
- Color / Typography / Layoutを別々に更新したくなった
- Template数が5種類以上になった
- AIが読む範囲を絞る必要が出た

分割後の候補:

```md
05_DESIGN_SYSTEM
├── 00_Design_System.md
├── 01_Design_Philosophy.md
├── 02_Color_System.md
├── 03_Typography.md
├── 04_Layout_System.md
├── 05_Component_Library.md
├── 06_Icon_System.md
├── 07_Motion_System.md
├── 08_LINE_Template.md
├── 09_A4_Template.md
├── 10_Dashboard_Template.md
├── 11_Mobile_App_Template.md
├── 12_Web_Template.md
└── README.md
```

## Phase 7: Brand Identity分離

目的:
Design Systemのさらに上に、Brand Identityを置く。

分離条件:
- HOTEL JOY、会社運営OS、MrBrainで共通世界観を明文化したくなった
- 「もっと温かい」「もっとミニマル」「もっと高級感」など、上位の雰囲気変更が増えた
- Design Tokenだけでは判断できない表現が増えた

作る候補:

```md
05_DESIGN_SYSTEM/00_Brand_Identity.md
```

ただし、現時点ではまだ作らない。
まずは`01_Design_Philosophy.md`内で扱えば十分。

## Next Best Action

次の一手:

```md
05_DESIGN_SYSTEM/00_Design_System.md を作る。
```

理由:
AIがDesign Systemを使う時の入口がないと、TokenやTemplateを作っても読み込み順序が安定しない。

最初の`00_Design_System.md`は短くする。
詳細を全部書かず、Design Routerとして機能させる。

## 作らないもの

現時点で作らない:

- 全Templateファイル
- 全Component Library
- 詳細なMotion System
- Brand Identity独立ファイル
- Web / Mobile App / Dashboardの完全仕様

理由:
まだ実案件Evidenceが不足している。
先に作るとDesign Systemが重くなる。

## 自己レビュー

Layer Leak:
なし。Design SystemはPresentation Layerとして扱い、Kernel / Principle / AI_CONTEXT / AGENTSには入れない。

責務重複:
注意が必要。TokenとTemplateが重複しやすい。Tokenは値、Templateは構造として分ける。

DesignとTemplateの違い:
Designは世界観と共通ルール。Templateは成果物ごとの型。

Presentation Layerとして自然か:
自然。Execution後、Humanへ届く前にPresentationを整える層として扱える。

AI Workspace OSとの整合性:
ある。AI Workspace OSがArtifactを決め、Design Systemが見せ方を統一する。

将来的にDesign変更が1箇所で済む構造か:
`00_Design_System.md`とTokenを正本にすれば可能。
ただし、Templateへ直接スタイルを書きすぎないことが条件。
