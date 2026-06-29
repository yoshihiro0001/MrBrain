# Operation Log

## 目的
Operation Logは、MrBrainで考えたことを現実で試し、その結果を戻すための記録場所である。

思想や発見を保存して終わらせず、実際に使った結果から次の接続を見つける。

## 位置づけ
```md
発見
↓
Blueprint
↓
Blueprint Review
↓
試す
↓
Operation Log
↓
結果測定
↓
Evolution Loop
↓
Blueprint更新
↓
Automation Backlog
```

## 使うタイミング
- MrBrainの考え方を現実で1回試した
- 経理、Booking.com、ホテル運営、AI連携、返信テンプレートを使った
- Codexに何か実装してもらった
- 試した結果、詰まった場所が見えた
- 同じ作業をまた繰り返しそうだと感じた

## 記録ルール
- 長く書かない
- 成功だけでなく、詰まった場所を書く
- 個人情報、税務情報、契約情報は丸写ししない
- 原本がある場合は、内容ではなく保管場所や索引を書く
- 次の1手まで必ず書く

## 今日の記録テンプレート
```md
## YYYY-MM-DD

### 今日試したこと
-

### 結果
-

### 詰まった場所
-

### 次の1手
-

### 関連Blueprint
- [[07_SYSTEM/Blueprint v2 Template]]

### Blueprint Reviewの結果
- [ ] 実装OKだった
- [ ] 修正して再レビューだった
- [ ] 保留だった
- 見落とし:

### 学習したこと
-

### Blueprintへ戻すこと
-

### Blueprint Engine / Reviewへ戻すこと
-

### Automation候補かどうか
- [ ] まだ候補ではない
- [ ] テンプレート化候補
- [ ] Codexスキル化候補
- [ ] アプリ化候補
- [ ] 外部サービス連携候補

### 戻す場所
-
```

## 記入例
```md
## 2026-06-25

### 今日試したこと
- Booking.com問い合わせ返信をHuman Communication OSの順番で整理した

### 結果
- 返信文をゼロから考える負担が減った

### 詰まった場所
- 実際の予約情報と返信テンプレートの接続場所がまだ決まっていない

### 次の1手
- Booking.com返信用Blueprintを1枚作る

### 関連Blueprint
- [[07_SYSTEM/Blueprint v2 Template]]

### Blueprint Reviewの結果
- [x] 実装OKだった
- 見落とし: 予約情報と返信テンプレートの接続場所が未定だった

### 学習したこと
- 返信文だけでなく、予約情報の取得場所まで設計に入れる必要がある

### Blueprintへ戻すこと
- Booking.com返信Blueprintに、予約情報の正本と確認方法を追加する

### Blueprint Engine / Reviewへ戻すこと
- ホテル返信では「返信文」と「実データの取得場所」を必ずセットで確認する

### Automation候補かどうか
- [x] テンプレート化候補
- [ ] Codexスキル化候補
- [ ] アプリ化候補
- [ ] 外部サービス連携候補

### 戻す場所
- [[02_PRINCIPLES/Human Communication OS]]
- [[03_BUSINESS/JOY/README]]
```

## 週次確認
週に1回、次を確認する。

- 同じ詰まりが3回出ていないか
- テンプレート化できる作業はないか
- Codexスキル化できる作業はないか
- アプリ化する前に、手動運用で十分ではないか
- MrBrainへ戻すべき判断基準はないか
