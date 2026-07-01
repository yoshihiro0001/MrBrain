# Design System Architecture Review

作成日: 2026-07-02

## 目的

AI Workspace OSで生成される全ての成果物を、共通デザインで出力できる構造を整理する。

対象成果物:
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

今回の目的は実装ではない。
Design Systemをどの責務で分けると、将来「一箇所の変更で全成果物へ反映」できるかをレビューする。

## 前提

土台として扱う既存資料:

- `デザイン引き継ぎファイル.md`
- `UI_DESIGN_GUIDELINES.md`
- `01_ME/好きなデザイン.md`

既存資料から読み取れる主要思想:

- ダーク & グラスモーフィズム
- スマホファースト
- 主役情報を大きく、脇役情報を控えめにする
- 余白をしっかり取り、関連情報をグループ化する
- Inter / Playfair Display / JetBrains Mono の役割分担
- 黒、白、透明度、エメラルド、赤、黄色を中心にする
- lucide系アイコンを控えめに使う
- ガラスカード、角丸、ボトムシート、滑らかなMotion
- 数値と付加情報は右揃えの縦並びで整理する
- ミニマルで、わかりやすく、余計な装飾が少ない

## 結論

`05_DESIGN_SYSTEM` は作る価値がある。

ただし、最初から細かいTemplateを増やしすぎると重くなる。

理想は次の階層。

```md
Brand Identity
↓
Design System
↓
Design Token
↓
Component / Pattern
↓
Template
↓
Presentation
↓
Artifact
```

DesignはExecutionではない。
AI Workspace OS上ではPresentation Layerとして扱うのが自然。

```md
Capability
↓
Execution
↓
Presentation
↓
Human
```

## 提案ディレクトリレビュー

提案構造:

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

レビュー:

この構造は最終形としては妥当。

ただし、最初から全ファイルを作ると重くなる可能性がある。
最初は`00_Design_System.md`を正本Indexにし、下位ファイルは必要になった順に作るのがよい。

## 00_Design_System.mdだけ読めば足りるか

結論:
80%は足りる構造にできる。
100%を目指すなら、`00_Design_System.md`は全文ルールではなく、Router / Index / Kernelとして設計する必要がある。

`00_Design_System.md`に持たせるべき内容:

- Brand Identityの短い要約
- Design Philosophyの短い要約
- Tokenの参照先
- Artifact別Templateの選び方
- 成果物生成時のDesign Check
- 禁止事項
- 迷った時の優先順位

`00_Design_System.md`に入れすぎないもの:

- 全Color Token詳細
- 全Typography詳細
- 全Component詳細
- Artifactごとの長いTemplate
- 実装コード

理想:

```md
AIはまず 00_Design_System.md を読む
↓
成果物タイプを判定
↓
必要な下位ファイルだけ読む
↓
Presentationを生成する
```

## Brand Identityの位置付け

Design Systemのさらに上には、Brand Identityを置くのが自然。

理由:
デザインは単なる見た目ではなく、思想やブランドを表現する手段だから。

推奨階層:

```md
Brand Identity
↓
Design System
↓
Template
↓
Presentation
```

Brand Identityで管理するもの:

- どんな印象を与えたいか
- 温度感
- 信頼感
- ミニマルさ
- 高級感
- 直感性
- HOTEL JOY / 会社運営OS / MrBrainに共通する世界観

現時点のBrand仮説:

```md
静かで高級感があり、ミニマル。
主役情報が明快で、余計な説明を減らす。
Human Agentが見た瞬間に動ける。
AI Workspace OSが出力しても、同じ世界観に揃う。
```

ただし、今すぐBrand Identityを独立ファイル化するかは保留。
最初は`01_Design_Philosophy.md`に含めてもよい。

## Design TokenとTemplateの関係

### Design Token

Design Tokenは、全成果物に共通する最小単位。

例:
- Color
- Typography
- Spacing
- Radius
- Shadow / Glass
- Icon size
- Motion duration
- Status color

Designを一箇所だけ変更して全成果物へ反映したいなら、Tokenは必須。

### Template

Templateは、成果物ごとの構造。

例:
- LINE Template
- A4 Template
- Dashboard Template
- Mobile App Template
- Web Template
- Mail Template

TemplateはTokenを使う。
Templateに独自の色や余白を直接書きすぎると、Design変更が分散する。

## Templateを持つべきか

結論:
両方必要。

```md
Design Token:
共通ルール

Template:
成果物ごとの型
```

AIが毎回Design Tokenだけから組み立てる方式は柔軟だが、出力がブレやすい。

一方、Templateだけだと硬くなり、成果物が増えるほど重複する。

最適案:

```md
Token
↓
Pattern
↓
Template
↓
Artifact
```

Templateは完成形の固定ではなく、AIが迷わないための型として扱う。

## 推奨する05_DESIGN_SYSTEM構造

初期構造:

```md
05_DESIGN_SYSTEM
├── 00_Design_System.md
├── 01_Design_Philosophy.md
├── 02_Design_Tokens.md
├── 03_Artifact_Templates.md
├── Design_System_Architecture_Review.md
├── Design_System_Roadmap.md
└── README.md
```

将来分割:

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

最初から分けすぎない理由:

- AIが読むファイルが増える
- TokenとTemplateの重複が起きる
- デザイン変更箇所が分散する
- まだ成果物ごとの実績が不足している

## 不足しているルール

既存のデザイン引き継ぎ資料に対して、Design System化するなら不足しているもの:

| 不足 | 理由 |
|---|---|
| Brand Identity | なぜそのデザインなのかの上位理由が必要 |
| Artifact別ルール | LINE / A4 / Dashboard / Mailでは読み方が違う |
| Design Token命名 | 色、余白、文字、角丸を再利用可能にするため |
| Light / Print対応 | A4やPDFは黒背景が不向きな場合がある |
| Human Agent向け簡易版 | 現場では美しさより迷わなさが重要 |
| Accessibility | 文字サイズ、コントラスト、スマホ可読性 |
| 状態表示 | 未確認、要確認、承認済み、危険、完了など |
| 禁止事項 | 写真やA4で文字を詰め込みすぎない等 |

## 重複しているルール

既存資料では次が重複している。

| 重複 | 統合先 |
|---|---|
| 数値と付加情報の配置 | Layout System / Component Pattern |
| 主役と脇役 | Design Philosophy / Typography |
| 余白とグループ化 | Layout System |
| 色の透明度 | Color System |
| アイコン方針 | Icon System |

重複自体は悪くないが、正本を一つにする必要がある。

## 統合できるルール

統合案:

```md
主役情報を大きく
補足情報を控えめに
関連情報を近く
危険情報は明確に
行動は一目で分かる
```

これはLINE、A4、Dashboard、App、Mailすべてに共通する。

## AI Workspace OSとの関係

将来の自然な流れ:

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
LINE / Web / App / Dashboard / PDF / A4 / Mail / 通知
```

この流れは自然。

理由:
- AI Workspace OSは「何を出すか」を決める
- Presentation Layerは「どう届けるか」を決める
- Design Systemは「どの世界観で見せるか」を決める

## Presentation Layerとして自然か

自然。

Design SystemはExecutionではない。
現実を直接変更するものではなく、ExecutionやArtifactをHumanが理解、承認、実行しやすい形に変換する層である。

```md
Capability
↓
Execution
↓
Presentation
↓
Human
```

ただし、Presentationの品質が低いとHumanが動けず、Executionが止まる。
その意味でDesign Systemは、AI Workspace OSの循環効率に直結する。

## DesignとTemplateの違い

| 項目 | 役割 |
|---|---|
| Design | 世界観、色、文字、余白、状態表現、視線誘導 |
| Template | 成果物ごとの構造、配置、セクション順 |
| Artifact | 実際に出力されるLINE文、A4、Dashboardなど |

Designは共通。
Templateは成果物別。
Artifactは毎回生成される実体。

## 00_Design_System.mdの理想内容

```md
1. Brand Identity要約
2. Design Philosophy要約
3. Token参照
4. Artifact別Template選択ルール
5. Presentation Check
6. 禁止事項
7. 迷った時の優先順位
```

迷った時の優先順位:

```md
1. Humanが迷わず動ける
2. 主役情報が一目で分かる
3. 余白とグループ化を守る
4. 世界観を統一する
5. 装飾を増やさない
```

## 自己レビュー

Layer Leak:
なし。Design SystemはPresentation Layerとして整理しており、Kernel / Principle / AI_CONTEXT / AGENTSには入れていない。

責務重複:
Design TokenとTemplateは重複しやすい。Tokenは共通値、Templateは成果物構造として分ける必要がある。

DesignとTemplateの違い:
明確。Designは世界観とルール、Templateは成果物ごとの型。

Presentation Layerとして自然か:
自然。Design SystemはExecutionではなく、Humanが理解しやすい表示へ変換する層である。

AI Workspace OSとの整合性:
ある。AI Workspace OSがArtifactを決め、Presentation LayerがDesign Systemを参照して出力を整える。

将来的にDesign変更が1箇所で済む構造か:
Tokenと00_Design_System.mdを正本にすれば可能。ただしTemplateへ直接スタイルを書きすぎると崩れる。

結論:
Design Systemは必要。ただし最初は小さく始める。
`00_Design_System.md`をDesign Routerにし、TokenとTemplateを段階的に分離するのが最も軽い。
