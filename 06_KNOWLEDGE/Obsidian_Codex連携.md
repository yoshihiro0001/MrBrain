# Obsidian Codex連携

## 目的
ObsidianをAIの永続メモリーとして使い、Codex、GitHub、Cursor、開発プロジェクトとつなげる。

## 文字起こしから得た要点
AIの出力が安定しない原因は、AIそのものだけではなく、記憶の設計にある。

Obsidianは、Markdownファイルをローカルに保存できるため、AIが読み取りやすい。

重要なのは、ただ情報を貯めることではない。
ルールを作り、整理し、AIが迷わない状態にすること。

## MrBrainでの意味
MrBrainは、Obsidian上の第二の脳であり、Codexに渡す永続メモリーでもある。

```md
Obsidian
↓
MrBrain
↓
AGENTS.md
↓
Codex
↓
GitHub
↓
開発・整理・分析
```

## なぜObsidian連携が重要か
- MarkdownなのでAIが読みやすい
- ローカルなので速い
- ファイル構造で整理できる
- GitHubに保存しやすい
- Codexが直接読める
- 同じ説明を繰り返さなくて済む

## ただ貯めるだけではダメ
情報を増やすだけでは、AIも人間も迷う。

必要なのは次の3つ。

1. 入口
   - `AGENTS.md`
   - `00_HOME/HOME.md`
   - `07_SYSTEM/AI_CONTEXT.md`

2. ルール
   - `07_SYSTEM/エネルギー循環OS憲法.md`
   - `07_SYSTEM/AI憲法.md`
   - `07_SYSTEM/セキュリティルール.md`
   - `07_SYSTEM/ファイル整理ルール.md`

3. 索引
   - `04_PROJECTS/スプレッドシート整理/5スプレッドシート_AI引き継ぎ.md`
   - `03_BUSINESS/会社マスター索引.md`
   - `04_PROJECTS/PROJECTS.md`
   - `03_BUSINESS/BUSINESS_INDEX.md`

## Codexに頼むと効果が高いこと
- MrBrain内の情報整理
- Markdown作成
- 既存ファイルの索引化
- スプレッドシート分析
- 開発プロジェクトの設計整理
- GitHub連携
- コード修正
- AGENTS.mdやAI_CONTEXTの更新

## Codexに頼むときの型
```md
AGENTS.mdを読んでから作業してください。

目的:

対象:

変更してよいファイル:

変更してはいけないファイル:

完了条件:

注意:
```

## Codexを便利に使うコツ
- まず「何をしたいか」より「何を壊したくないか」を伝える
- 大きな相談は、最初に現状分析だけ頼む
- 実装前に設計意図を説明させる
- 変更したら、必ずMrBrainに記録させる
- GitHubへ保存する前に、個人情報チェックを頼む
- 1回の依頼で、整理・実装・検証・記録までやらせる

## 役割分担
| ツール | 役割 |
|---|---|
| Obsidian | 読む、考える、つなげる |
| MrBrain | 自分専用の永続メモリー |
| Codex | 整理、実装、検証、記録 |
| GitHub | 履歴、バックアップ、開発連携 |
| Cursor | コード編集やアプリ開発 |
| Google Drive | 原本、スプレッドシート、証憑 |

## 注意
Obsidianは便利だが、情報を入れすぎると重くなる。

MrBrainでは、原本を全部入れない。
要約、索引、保管場所、判断だけを入れる。
