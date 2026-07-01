# Animation Taste Test

作成日: 2026-07-02

## 目的

Animation Systemを確定する前に、Motionの好みとズレを確認する。

これはAnimation System本体ではない。
採用前のTaste Testである。

確認したいこと:
- 自分の好みに合うか
- シンプルか
- 丸い印象か
- 心地よいか
- 余白と相性が良いか
- 操作を邪魔しないか
- 情報理解が早くなるか

## 1. 好き / 苦手 チェック表

| 項目 | 好き候補 | 苦手候補 | 判定 |
|---|---|---|---|
| 速度 | 短い、反応が早い | 長い、待たされる | 未確認 |
| 印象 | 静か、滑らか、上品 | 派手、騒がしい、跳ねる | 未確認 |
| 目的 | 状態が分かる | 何のためか分からない | 未確認 |
| 触感 | Buttonが軽く沈む | 大きく跳ねる、派手に膨らむ | 未確認 |
| 表示 | Fade + 少し移動 | 大きな移動、回転 | 未確認 |
| Loading | Skeleton、進捗説明 | 無限Spinnerだけ | 未確認 |
| Error | 読める、理由が分かる | 揺れ続ける、読みにくい | 未確認 |
| Success | 短いCheck | 長い演出 | 未確認 |
| Page | 文脈が保たれる | 画面が大きく動きすぎる | 未確認 |

## 2. Motion候補

### 採用候補

- Fade
- Small Slide
- Subtle Scale
- Short Success Check
- Soft Dialog Rise
- Light Card Stagger
- Skeleton
- Reduced Motion対応

### 保留

- Spring
- Layout shared transition
- View Transition API
- Scroll-linked animation
- Parallax
- Drag gesture

### 禁止候補

- Strong Bounce
- Elastic過多
- Infinite decorative loop
- Big rotate
- Big zoom
- Long loading animation
- Motion-only explanation

## 3. Artifact別Taste確認

| Artifact | Motionを使うか | Taste確認 |
|---|---|---|
| LINE | 使わない | 改行、記号、余白でリズムを作る |
| A4 | 使わない | Icon、余白、チェックで視線誘導 |
| PDF | 使わない | 印刷可読性優先 |
| Mail | 使わない | 段落と見出し優先 |
| Web | 使う | Hover、Card、Dialog、Page Transition |
| App | 使う | Press、Dialog、Success、Notification |
| Dashboard | 控えめに使う | 状態変化と重要通知だけ |
| Mobile Approval | 使う | Button pressとSuccessのみで十分か確認 |

## 4. Sample確認項目

### Sample 1: Button Press

確認:
- 押した感覚があるか
- Scaleが大きすぎないか
- 反応が遅くないか

好み候補:

```md
scale 0.98
duration 80〜120ms
```

### Sample 2: Card Enter

確認:
- 表示されたことが自然に分かるか
- 余白と相性が良いか
- 動きすぎないか

好み候補:

```md
opacity 0 → 1
translateY 6px → 0
duration 160〜220ms
```

### Sample 3: Dialog

確認:
- 視線が自然に集まるか
- 圧迫感がないか
- 操作を邪魔しないか

好み候補:

```md
backdrop fade
panel translateY 12px → 0
duration 180ms
```

### Sample 4: Success

確認:
- 完了が分かるか
- 長すぎないか
- 次Actionにすぐ進めるか

好み候補:

```md
check opacity + small scale
duration 160〜220ms
```

### Sample 5: Page Transition

確認:
- どこへ移動したか分かるか
- 大きく動きすぎないか
- 戻る時に違和感がないか

好み候補:

```md
fade + small slide
duration 200〜240ms
```

## 5. 質問リスト

実サンプルを見た時に確認する質問:

1. この動きは気持ちいいか。
2. この動きで意味が分かりやすくなったか。
3. 動きがない方が見やすいか。
4. 速すぎるか、遅すぎるか。
5. 丸すぎるか、硬すぎるか。
6. 高級感があるか、安っぽく見えるか。
7. 仕事中に毎日見ても疲れないか。
8. Human Agentが迷わず動けるか。

## 6. 採用候補 / 保留 / 禁止候補

### 採用候補

- Short Fade
- Small Slide
- Press Scale 0.98
- Success Check
- Subtle Skeleton
- Reduced Motion対応

### 保留

- Spring
- Page shared transition
- Card Stagger
- View Transition API
- Gesture animation

### 禁止候補

- 派手なBounce
- 目立つだけのLoop
- 長いLoading
- 読めないAnimation
- 大きな回転
- 画面全体の強いZoom
- Error Shakeの多用

## 7. 次に作るべき小さなAnimation Sample

Design System確定前に、次の5サンプルを作る。

1. Button Press
2. Card Enter
3. Dialog Open / Close
4. Success Check
5. Page Transition

最初に作るなら:

```md
Mobile ApprovalのButton Press + Success Check
```

理由:
AI Workspace OSの最終ビジョンでは、Humanがスマホで承認することが最重要だから。

## Taste Test結論

現時点では、Animation Systemを確定しない。

まず確認すべきズレ:

1. Springが心地よいか、柔らかすぎるか。
2. Fade + Small Slideだけで十分か。
3. Page Transitionは必要か。
4. DashboardでCard Staggerが気持ちいいか、邪魔か。
5. Success演出はどの長さが最も気持ちいいか。

## 自己レビュー

Layer Leak:
なし。これはAnimation System確定前の好み検証であり、Kernel / Principle / AI_CONTEXT / AGENTSには入れない。

Design System本体との関係:
本体ではない。採用前のチェックシート。

Presentation Layerとして自然か:
自然。MotionはHumanへ状態変化を伝えるためのPresentationである。

次の一手:
Mobile Approval用に、Button PressとSuccess Checkの小さなサンプルを作る。
