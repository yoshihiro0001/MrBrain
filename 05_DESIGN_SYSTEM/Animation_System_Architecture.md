# Animation System Architecture

作成日: 2026-07-02

## 目的

AI Workspace OSで生成されるWeb、App、Dashboard、LINEなどの成果物で、一貫したMotionを使えるようにする。

Animationはライブラリではない。
Design Systemの一部として管理する。

```md
Brand Identity
↓
Design System
↓
Animation System
↓
Presentation
↓
Artifact
```

重要:
固定するのはAnimation Ruleであり、ライブラリではない。

```md
Animation Rule
↓
Library / Platform
```

将来Framer Motion / Motionより良いものが出ても、Ruleを変えずに実装だけ差し替えられる構造を目指す。

## Animation Philosophy

Animationは、美しさだけのために存在しない。

Animationは、

- 理解を早める
- 操作を気持ちよくする
- 状態変化を伝える
- 待ち時間の不安を下げる
- Human Agentが次に何をすべきか分かる

ために存在する。

Motionは装飾ではなく、Presentation Layerにおける状態説明である。

## Brandとの関係

現在のDesign Tasteから見ると、Animationは次の方向が合う可能性が高い。

- 派手ではない
- 短い
- 意味がある
- 滑らか
- 余白と相性が良い
- 触った時に気持ちいい
- 操作を邪魔しない
- 情報理解が早くなる

避ける方向:

- 過度なBounce
- 長い演出
- 意味のないLoop
- 派手な画面切替
- 読む前に動きすぎるUI

## 2026年時点の実装選択レビュー

| 技術 | 位置付け | 向いている用途 | 注意 |
|---|---|---|---|
| Motion / Motion for React | Reactの主要候補。旧Framer Motion系 | Dashboard、App、カード、Dialog、Layout変化、Gesture | ライブラリ依存にしすぎない |
| CSS Transition / Animation | 最軽量なWeb標準 | Hover、Button、色、Opacity、軽いTransform | 複雑な状態管理には弱い |
| Web Animations API | ブラウザ標準API | JS制御が必要なWeb Animation | React stateとの統合設計が必要 |
| View Transition API | 画面 / View間の遷移 | Page Transition、SPA/MPAの画面切替 | 対応状況とFallback確認が必要 |
| Native Animation | iOS / Androidの標準Animation | Native App | Platform差分がある |
| React Native Animated / LayoutAnimation | React Native向け | AppのUI Motion、Layout変化 | Native Driver制約やLayoutAnimation制御差分に注意 |

2026年時点の判断:

```md
単純なHover / Button:
CSS

React UIの状態変化:
Motion

画面遷移:
View Transition APIまたはFramework標準 + Motion

Native App:
Native Animation / React Native Animated

LINE / Mail / A4:
基本はAnimationなし。構造、余白、アイコンでMotionの代わりをする。
```

## Animation Rule

### 画面遷移

目的:
今どこへ移動したかを理解しやすくする。

Rule:
- 方向性がある遷移だけ動かす
- 画面全体を派手に動かさない
- Fade + 軽いSlideを基本にする
- 戻る操作は逆方向にする
- 300msを超えないことを基本にする

推奨:

```md
opacity 0 → 1
translateY 8px → 0
duration 180〜240ms
```

### カード表示

目的:
新しい情報が追加されたことを自然に伝える。

Rule:
- Fade + 微小なY移動
- Scaleは使ってもごく小さく
- 複数カードはStaggerを短くする

推奨:

```md
opacity 0 → 1
translateY 6px → 0
duration 160〜220ms
stagger 30〜50ms
```

### Hover

目的:
押せる、触れる、選べることを伝える。

Rule:
- 背景を少し明るくする
- Shadow / Border / Glassの強さを少し変える
- Scaleは最大でも1.01〜1.02
- Hoverだけで情報を隠さない

推奨:

```md
duration 100〜160ms
scale 1.00 → 1.01
background alpha +0.04
```

### Button

目的:
操作した感覚を返す。

Rule:
- Tap / Pressは短く沈む
- 成功時だけ状態変化を返す
- Loading中は連打を防ぐ

推奨:

```md
tap scale 0.98
duration 80〜120ms
```

### Dialog

目的:
注意が必要な状態へ視線を集める。

Rule:
- Backdropは短くFade
- Dialogは下から少し上がるか、中央で微小Scale
- 危険系Dialogは動きを派手にせず、色とIconで伝える

推奨:

```md
backdrop opacity 0 → 1 / 120ms
panel opacity 0 → 1 / translateY 12px → 0 / 180ms
```

### Success

目的:
完了した安心を短く伝える。

Rule:
- Check Iconを短く表示
- Green / Emeraldを使う
- 長く残さない
- 成功演出で次Actionを邪魔しない

推奨:

```md
check scale 0.9 → 1.0
opacity 0 → 1
duration 160〜220ms
```

### Error

目的:
止まった理由と次Actionを伝える。

Rule:
- Shakeは原則使わない
- Red / Alert Icon / Borderで伝える
- Error文は動かさず読める状態にする
- 次に何を直すかを固定表示する

推奨:

```md
error panel fade in 120〜160ms
no loop
no shake unless very small
```

### Loading

目的:
待機中であることを伝え、不安を下げる。

Rule:
- 長いLoadingは避ける
- 可能ならSkeletonを使う
- 進捗が分かる場合はProgressを出す
- 無限Spinnerだけで放置しない

推奨:

```md
0〜500ms:
何も出さない、またはButton内Loading

500ms〜2s:
Skeleton / small spinner

2s以上:
状態説明 + 次Action
```

### Notification

目的:
重要な変化を短く伝える。

Rule:
- Slideしすぎない
- 3〜5秒で消える
- Error / Approval待ちは勝手に消さない
- Actionがある通知は固定する

推奨:

```md
opacity 0 → 1
translateY -8px → 0
duration 160〜220ms
```

### Skeleton

目的:
読み込み中の構造を先に見せる。

Rule:
- 実際のLayoutに近い形にする
- shimmerは控えめ
- 点滅しすぎない
- 長く続く場合は説明を出す

推奨:

```md
subtle shimmer 1.2〜1.8s
alpha low
no strong contrast
```

### Page Transition

目的:
文脈を失わず、画面が切り替わったことを伝える。

Rule:
- View Transition APIやFramework標準が使える場合は検討
- ただし、古い環境ではFade fallback
- 画面全体の大きなScaleは避ける
- 戻る / 進む方向を統一する

推奨:

```md
fade + small slide
duration 180〜260ms
fallback: opacity only
```

## Motion Time

| 種類 | 時間 | 用途 |
|---|---:|---|
| Instant | 0〜80ms | 状態切替、押下感 |
| Short | 100〜160ms | Hover、Button、軽いFeedback |
| Normal | 180〜240ms | Card、Dialog、Notification |
| Long | 260〜360ms | Page Transition、重要な状態変化 |
| Avoid | 400ms以上 | 原則避ける。説明が必要な場合のみ |

標準:

```md
Micro interaction:
120ms

UI transition:
180〜220ms

Page transition:
240ms前後
```

## Easing

基本:

```md
ease-out:
表示、出現、完了

ease-in:
消える、閉じる

ease-in-out:
画面遷移、状態切替

spring:
軽いPressやDragなど、触感が必要な時だけ
```

禁止:
- 強いBack
- 過度なElastic
- 派手なBounce

## Accessibility

Motionは必ずReduced Motionに対応する。

Rule:
- `prefers-reduced-motion` を尊重する
- Reduced Motionでは、移動、Scale、Parallaxを減らす
- 必要な状態変化はOpacityやInstant表示に置き換える
- Motionなしでも意味が伝わるようにする

Reduced Motion時:

```md
translate / scale:
off

opacity:
allowed

duration:
0〜80ms

loop:
off
```

## Artifact別方針

| Artifact | Motion方針 |
|---|---|
| LINE | Motionなし。絵文字、改行、区切りでリズムを作る |
| A4 | Motionなし。余白、Icon、チェックで視線誘導 |
| PDF | Motionなし。Layoutで理解を早める |
| Mail | Motionなし。段落と見出しで整理 |
| Web | CSS / Motion / View Transitionを使い分け |
| App | Native / Motion / React Native Animatedを使い分け |
| Dashboard | 状態変化、カード追加、通知に限定 |
| Mobile Approval | Button press、Dialog、Successに限定 |

## Library Selection Rule

ライブラリは固定しない。

選定順:

```md
1. Animation Ruleを確認
2. Artifactを確認
3. Platformを確認
4. 最軽量の実装を選ぶ
5. 複雑な状態変化だけMotion系を使う
```

Web / React:
- HoverやButtonはCSSで十分
- Layout変化、Exit animation、Gesture、複雑な状態変化はMotion候補
- Page TransitionはView Transition APIも検討

Native:
- Platform標準Animationを優先
- React NativeではAnimated / LayoutAnimationを検討

Print / Text:
- Animation不要
- Motionの代わりにLayout Rhythmを使う

## 禁止事項

- 意味のないLoop
- 派手なBounce
- 長いLoading
- 読めないAnimation
- 操作を邪魔するMotion
- Motionがないと意味が分からないUI
- Error文を揺らし続ける
- LoadingをSpinnerだけで放置する
- A4 / PDF / MailへMotion前提の考えを持ち込む
- ライブラリ都合でMotion Ruleを変える

## Design Systemとの整合性

Design Taste Testと一致する点:
- 派手ではない
- 短く意味がある
- 操作を邪魔しない
- 余白とグループ化を優先する
- ロゴっぽい強さ、見やすさを壊さない

Design System Architectureと一致する点:
- AnimationはDesign Tokenの一種として管理できる
- Templateに直接Motionを書きすぎない
- Presentation Layerとして扱う
- ArtifactごとにMotion有無を切り替える

## 参考情報

2026-07-02時点で確認した一次情報:

- Motion for React documentation: `https://motion.dev/docs/react`
- MDN View Transition API: `https://developer.mozilla.org/en-US/docs/Web/API/View_Transition_API`
- MDN prefers-reduced-motion: `https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-reduced-motion`
- MDN Web Animations API: `https://developer.mozilla.org/en-US/docs/Web/API/Web_Animations_API/Using_the_Web_Animations_API`
- React Native Animations: `https://reactnative.dev/docs/animations`

読み取り:
- Motion for Reactは旧Framer Motion系のReact向けAnimation候補。
- View Transition APIは画面やView間の文脈維持に向く。
- prefers-reduced-motionは必須のAccessibility前提。
- React NativeではAnimatedとLayoutAnimationを用途で分ける。

## 自己レビュー

Layer Leak:
なし。Animation SystemはDesign System内のPresentation Layerとして扱う。

Designとの整合性:
ある。Design Taste Testの「派手ではなく、意味があり、心地よいMotion」と一致する。

Presentation Layerとして自然か:
自然。AnimationはExecutionではなく、Humanへ状態変化を伝えるPresentationである。

Brand Identityとの整合性:
ある。静かで高級感があり、ミニマルで直感的な方向に合わせる。

2026年時点でベストプラクティスか:
概ね妥当。Motion / CSS / View Transition API / Native Animationを用途別に扱い、Ruleをライブラリより上位に置いている。

今後の注意:
ライブラリの流行に合わせてDesign Ruleを変えない。
Ruleを維持し、実装だけ差し替える。
