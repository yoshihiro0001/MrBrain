# 文字起こし ObsidianとAI永続メモリー

## 元資料
Codex添付の文字起こし。

テーマ:
ObsidianをAIエージェントの第二の脳として使い、Codex、Claude Code、Cursor、Antigravityなどと連携する考え方。

## 要点
AIがうまく動かない原因は、AIの性能だけではなく、記憶の設計にある。

同じ説明を何度もする、AIが前回の作業を忘れる、アウトプットが安定しない、という問題は、AIに渡す前提情報が整理されていないことから起きる。

## Obsidianが重要な理由
- MarkdownなのでAIが読みやすい
- ローカルにあるため速い
- フォルダとリンクで整理できる
- AIの長期記憶として使いやすい
- Codex、Claude Code、Cursorなど複数ツールで共有できる

## ただ保存するだけでは足りない
情報をObsidianに貯めるだけでは不十分。

重要なのは次の3つ。

1. 記憶を設計する
2. ルールを作る
3. 使いながら整える

MrBrainでは、これを次の形で実装する。

- 入口: `AGENTS.md`
- 背景: `07_SYSTEM/AI_CONTEXT.md`
- 憲法: `07_SYSTEM/エネルギー循環OS憲法.md`
- 安全: `07_SYSTEM/セキュリティルール.md`
- 索引: `04_PROJECTS/PROJECTS.md`、`03_BUSINESS/BUSINESS_INDEX.md`
- 記録: `07_SYSTEM/DECISION_LOG.md`
- タスク: `00_HOME/TASKS.md`

## AIエージェントを育てる考え方
AIに知識を足すだけではなく、次回からどう動くかをルール化する。

例:
- 次から作業前に `AGENTS.md` を読む
- 変更したら必ず記録する
- 新しいタスクは `TASKS.md` に入れる
- 重要決定は `DECISION_LOG.md` に残す
- 個人情報や税務情報を丸写ししない

## MrBrainへの反映
この文字起こしの内容は、MrBrainにすでに反映した。

反映先:
- [[AGENTS]]
- [[06_KNOWLEDGE/Obsidian_Codex連携]]
- [[06_KNOWLEDGE/Codex便利な使い方]]
- [[04_PROJECTS/MrBrain_GitHub_Obsidian_Codex連携計画]]
- [[04_PROJECTS/GitHub連携_MrBrain保存計画]]

## Codexでの実用ルール
Codexに頼むときは、まず次の形にする。

```md
AGENTS.mdを読んでから作業してください。

目的:
対象:
変更してよいファイル:
変更してはいけないファイル:
完了条件:
注意:
```

## 自分への結論
Obsidian連携を強く望むのは正しい。

理由:
- 同じ説明を繰り返さなくて済む
- AIの文脈が安定する
- Codex、Cursor、GitHubとの接続がしやすい
- MrBrainがエネルギー循環OSの実験機になる

## 注意
Obsidianを便利にするために、情報を増やしすぎない。

重要なのは、保存量ではなく構造。

MrBrainでは、原本ではなく、索引・要約・判断・保管場所を保存する。
