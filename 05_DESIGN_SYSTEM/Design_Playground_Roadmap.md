# Design Playground Roadmap

作成日: 2026-07-02

## 目的

Design Playgroundを、Designを眺める場所ではなく、Designを決める場所へ育てる。

最終的には、UserがPlaygroundで承認したDesign Tokenが、LINE、A4、Dashboard、Web、Mobile App、Human Agent Mission、通知、PDFなど全Artifactへ反映される状態を目指す。

## Phase 0: Documentation

状態:
完了候補。

作るもの:
- `Design_Playground.md`
- `Design_Playground_Roadmap.md`

目的:
Design Playgroundの責務を明確にする。

成功条件:
- Design Taste Testとの違いが明確
- Design Systemとの責務が明確
- Compare Modeが定義されている
- Token変更が全Artifactへ反映される将来像がある

## Phase 1: Static Playground Prototype

作るもの:

```md
05_DESIGN_SYSTEM/playground/index.html
```

目的:
Design Tokenを切り替え、ComponentとArtifact Previewを実際に見る。

含めるもの:
- Theme切り替え
- Spacing切り替え
- Radius切り替え
- Shadow切り替え
- Glass切り替え
- Animation Speed切り替え
- Animation Style切り替え
- Typography切り替え
- Component Preview
- Artifact Preview
- Compare Mode

成功条件:
- ブラウザで開ける
- Design方向を直感的に比較できる
- どのTokenが見た目に影響しているか分かる
- Mobile Approvalの方向が確認できる

## Phase 1.5: Design Decision Experience v2

目的:
設定画面から、Humanが心地よくDesignを決める体験へ進化させる。

v1の課題:
- 専門用語が多い
- 左の設定パネルとPreviewの距離が遠い
- Token値を選ぶ体験になっている
- Humanが何を判断すればよいか分かりにくい

v2の方針:

```md
1画面1判断
↓
体験の言葉で質問
↓
A/B/C比較
↓
変更前 / 変更後Preview
↓
好き / 違うで選ぶ
↓
暫定Design Tokenへ変換
```

最初に扱う判断:
- Spacing
- Radius
- Motion
- Glass
- Typography

成功条件:
- Human AgentがDesign用語を知らなくても判断できる
- 「どちらが好きか」で選べる
- Previewで差分がすぐ分かる
- 最後に暫定Design Tokenがまとまる
- Design Decision Logへつなげられる

このPhaseでは、まだhotel_systemへ移植しない。
MrBrain内の静的HTMLで体験改善を確認する。

## Phase 2: Token Export

目的:
Playgroundで選んだ設定をDesign Tokenとして保存できるようにする。

候補:

```md
design-token-candidate.json
```

保存するもの:
- theme
- spacing
- radius
- shadow
- glass
- motion.speed
- motion.style
- typography
- icon library

注意:
この段階でも、まだ正本Tokenではない。
Userが承認したものだけDesign Systemへ昇格する。

## Phase 3: Artifact Binding

目的:
Token変更がArtifact Previewへ自然に反映される構造を作る。

対象:
- LINE
- A4
- Human Agent Mission
- Dashboard
- Web
- Mobile
- Mail
- PDF
- 通知
- Blueprint

方針:
ArtifactごとにToken適用範囲を変える。

例:
- LINE: spacing / typography rhythm / icon tone
- A4: spacing / icon / status color
- Dashboard: theme / glass / shadow / radius / motion
- Mobile: radius / spacing / motion / approval state

## Phase 4: Compare Mode

目的:
Userが重要な判断と承認だけ行えるようにする。

構造:

```md
AIがA案 / B案 / C案を生成
↓
Playgroundで横並び表示
↓
Userが選ぶ
↓
選択理由を記録
↓
Design Systemへ反映候補として保存
```

Compare対象:
- Button
- Approval Card
- Mission Card
- Dashboard Widget
- A4 Mission
- LINE Mission

## Phase 5: Design Decision Log

目的:
なぜそのDesign Tokenになったかを後から分かるようにする。

記録するもの:
- Decision date
- Token
- Before / After
- 選んだ理由
- 合わなかった案
- 影響Artifact
- 戻す理由

これはGit commitとは別。
Gitは履歴、Design Decision Logは判断の意味を残す。

## Phase 6: App化

目的:
Design Playgroundを継続的に使える内部アプリへ育てる。

候補:
- Cursor / CodexでReact Appとして実装
- Design TokenをJSONとして管理
- Artifact PreviewをComponent化
- Snapshotと連携

ただし、今はまだ本格App化しない。

理由:
- Design Tasteが未確定
- Artifact実績が不足
- Token正本がまだない

## 2026年時点のMotion実装方針

確認した一次情報からの判断:

- Motion for Reactは、React UI Animationの主要候補。旧Framer Motion系で、React state、layout、gesture、exit animationに強い。
- CSS Transitionは、HoverやButtonなど単純なMotionに最も軽い。
- View Transition APIは、画面やView遷移の文脈維持に向くが、Fallback前提で扱う。
- Native AppではPlatform標準Animationを優先する。

結論:

```md
Ruleを固定する。
Libraryは差し替え可能にする。
```

参考情報:
- Motion for React: `https://motion.dev/docs/react`
- MDN View Transition API: `https://developer.mozilla.org/en-US/docs/Web/API/View_Transition_API`
- MDN prefers-reduced-motion: `https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-reduced-motion`
- React Native Animations: `https://reactnative.dev/docs/animations`

## Risk

| Risk | 対策 |
|---|---|
| Playgroundが遊び場になりすぎる | Design Decision Platformとして、承認と記録を中心にする |
| Tokenが増えすぎる | 最初はTheme / Spacing / Radius / Shadow / Motion / Typographyだけ |
| ArtifactごとにDesignがバラつく | Artifact Previewを同時に見る |
| Motionが派手になる | Animation Systemの禁止事項を適用する |
| Compare案が多すぎる | A / B / Cまでに制限する |

## Next Best Action

最初に行うこと:

```md
Static Playground Prototypeを開き、Mobile Approval CardのA/B/Cを比較する。
```

理由:
Humanが承認だけで進めるOSにおいて、Mobile Approvalの体験が最重要だから。
