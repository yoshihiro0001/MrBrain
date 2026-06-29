# MrBrain Evolution Map

## 目的
MrBrainの進化を、commit履歴ではなく「どの能力が追加されたか」で追えるようにする。

Gitは保存手段。
Evolution Mapは、MrBrain開発の正本である。

未来の自分とAIが、
「いつに戻るか」ではなく、
「どの能力に戻るか」
で判断できる状態を作る。

## 現在のVersion
```md
MrBrain v0.4
```

現在地:
- GitHub保存完了
- Snapshot運用開始
- AGENTS / Kernel RouterにGit運用導線を接続済み
- 次は、実運用で「編集前後commit」と「大きな編集前後snapshot」を試す段階

## 能力一覧
| 状態 | 能力名 | 目的 | 正本 / 入口 | Snapshot名 | Git tag | 完成日 | 現在Version |
|---|---|---|---|---|---|---|---|
| [x] | Obsidian Vault化 | MrBrainをMarkdownで扱える第二の脳にする | `00_HOME/HOME.md` | 未設定 | 未設定 | 2026-06-22 | v0.1 |
| [x] | AI起動入口 | AIが作業前に読む入口を固定する | `AGENTS.md` | 未設定 | 未設定 | 2026-06-23 | v0.1 |
| [x] | AI_CONTEXT | 毎回AIが読む短い現在地を作る | `07_SYSTEM/AI_CONTEXT.md` | 未設定 | 未設定 | 2026-06-23 | v0.1 |
| [x] | Runtime Loop | 判断、設計、実行、学習を循環させる | `07_SYSTEM/MrBrain Runtime Loop.md` | 未設定 | 未設定 | 2026-06-27 | v0.2 |
| [x] | Kernel Router | 最小トークンで必要なLibrary / ProjectへRoutingする | `07_SYSTEM/MrBrain Kernel Router.md` | 未設定 | 未設定 | 2026-06-28 | v0.3 |
| [x] | Layer Integrity Check | Project具体例が上位へ漏れないよう自己監査する | `07_SYSTEM/MrBrain Kernel Router.md` | 未設定 | 未設定 | 2026-06-29 | v0.3 |
| [x] | GitHub保存 | AI編集後に戻せる履歴管理を作る | `04_PROJECTS/GitHub連携_MrBrain保存計画.md` | `snapshot-20260629-mrbrain-github-initial-sync` | `snapshot-20260629-mrbrain-github-initial-sync` | 2026-06-29 | v0.4 |
| [x] | Snapshot復元ルール | commit hashではなく意味ある名前で戻れるようにする | `07_SYSTEM/MrBrain 保存・復元・拡張ルール.md` | `snapshot-20260629-mrbrain-github-initial-sync` | `snapshot-20260629-mrbrain-github-initial-sync` | 2026-06-29 | v0.4 |
| [x] | Git運用導線 | Codexが毎回保存・復元ルールを忘れないようにする | `AGENTS.md` / `07_SYSTEM/MrBrain Kernel Router.md` | 未設定 | 未設定 | 2026-06-29 | v0.4 |

## Snapshot対応表
| Snapshot名 | 能力名 | 目的 | 戻る理由 | Git tag | 対応commit |
|---|---|---|---|---|---|
| `snapshot-20260629-mrbrain-github-initial-sync` | GitHub保存 / Snapshot復元ルール | MrBrainをGitHubへ安全に保存し、意味ある名前で復元できるようにする | Git導入や復元ルール周辺で壊れた時、この安定地点へ戻る | `snapshot-20260629-mrbrain-github-initial-sync` | `a413c33` |

## 次に育てる能力
| 優先 | 能力名 | 目的 | 成功条件 | Snapshot候補 |
|---:|---|---|---|---|
| 1 | AI編集前後commit運用 | 実際のCodex編集で、変更前後の保存が自然に回るようにする | 1回の編集で `status → diff → commit → push` が問題なく回る | `after-YYYYMMDD-ai-edit-commit-flow` |
| 2 | JOY 202号室信号調査 | JOY売上源流の最小観測点を見つける | 202号室の現場動作からPC処理までの対応表ができる | `after-YYYYMMDD-joy-202-signal-map` |
| 3 | Approval Inbox / Command Center | AI提案を1つの承認画面に集める会社運営OSの入口を作る | 汎用コンポーネントと最初のMVP対象が決まる | `after-YYYYMMDD-approval-inbox-blueprint` |
| 4 | MrBrain運用ログの定着 | 保存して終わりではなく、実行結果を戻す | Operation Logを1回実運用する | `after-YYYYMMDD-operation-log-first-use` |

## Versionの考え方
| Version | 意味 |
|---|---|
| v0.1 | Vault骨格とAI入口ができた |
| v0.2 | Runtime LoopでOSとして回る考え方が入った |
| v0.3 | Kernel Routerで最小読み込みとRoutingができた |
| v0.4 | GitHub保存とSnapshot復元ができた |
| v0.5 | 実運用でcommit / snapshot / recoveryが自然に回る |

## Snapshot作成時の記録テンプレート
Snapshotを作る時は、commit hashだけで終わらせない。

必ず、次の形でEvolution Mapにも記録する。

```md
## Snapshot記録
- Snapshot名:
- Git tag:
- 能力名:
- 目的:
- 戻る理由:
- 作成日:
- 対応commit:
- 関連ファイル:
```

## Snapshot命名ルール
安定地点:
```md
snapshot-YYYYMMDD-内容
```

大きな作業前:
```md
before-YYYYMMDD-作業名
```

大きな作業後:
```md
after-YYYYMMDD-作業名
```

## 運用ルール
- commitは細かい保存
- snapshotは意味のある復元地点
- Evolution Mapは能力の進化履歴
- 大きな能力が追加されたら、このMapを更新する
- snapshotを作ったら、Snapshot対応表にも追記する
- 迷ったら「どの能力に戻りたいか」で判断する
