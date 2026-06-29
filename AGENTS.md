# MrBrain AGENTS

## 必ず読む
- `07_SYSTEM/MrBrain Kernel Router.md`
- `07_SYSTEM/AI_CONTEXT.md`
- `00_HOME/TASKS.md`

## 実行原則
MrBrainは、Kernel、Router、Library、Projectの4層で扱う。

毎回すべてを読まない。
Routerが、必要なLibraryとProjectだけを選ぶ。

基本順序:
```md
Goal
↓
Success Condition
↓
Source First
↓
Hypothesis
↓
Minimal Information
↓
Route
↓
Output
↓
Learn
```

## 判断基準
- シンプルを優先
- 長期運用を優先
- 人力を減らす
- 同じ説明を繰り返さない
- 情報は構造化して保存する
- 下流より先に源流を見る
- 最小入力で最大推論し、不足分だけ確認する

## 安全
個人情報、税務、契約、給与、秘密情報は省略しない。

パスワード、APIキー、秘密鍵は書かない。

削除、移動、外部公開、大きな実装は事前に確認する。

## 記録先
| 内容 | 保存先 |
|---|---|
| 毎回AIが読む短い現在地 | `07_SYSTEM/AI_CONTEXT.md` |
| 重要な決定 | `07_SYSTEM/DECISION_LOG.md` |
| 新しいタスク | `00_HOME/TASKS.md` |
| 実験、運用結果 | `07_SYSTEM/Operation Log.md` |
| 対象別Blueprint | `04_PROJECTS` |

## 実装ルール
大きな実装は、BlueprintとBlueprint Reviewを通してから行う。

小さな修正は、目的、影響範囲、戻し方を確認してから行う。

変更した内容は、必要に応じて記録する。

## 禁止
- 新しいPrincipleを増やさない
- Blueprintを量産しない
- 既存UI再現を目的にしない
- 安全確認を省略しない
- 思考を長文化しすぎない
