# NotebookLMの役割

## 目的
NotebookLMを何に使い、何に使わないかを整理する。

## 2026-06-23の気づき
最初はNotebookLMを記憶装置のように考えていた。

しかし、実際にはNotebookLMは長期保存先ではなく、ソースをもとに調べたり学んだりするための知識検索AIとして扱うのがよい。

## NotebookLMで保存されるもの
保存される可能性が高いもの:
- Notebook自体
- Notebook名
- 追加したソース
- YouTube
- PDF
- Markdown
- Google Docsなどの資料

## 注意が必要なもの
NotebookLM上の会話は、ChatGPTやMrBrainのように長期記憶として積み上げる前提にしない。

そのため、重要な気づきや判断はMrBrainに保存する。

## 役割分担
```md
NotebookLM
↓
学ぶ・調べる・ソースに質問する

ChatGPT
↓
考える・整理する・壁打ちする

Codex
↓
MrBrainへ保存する・実装する・検証する

MrBrain
↓
蓄積する・正本にする・後からAIに渡す
```

## 一番シンプルな運用
```md
NotebookLM
学ぶ
↓
ChatGPT
整理する
↓
Codex
保存する
↓
MrBrain
蓄積する
```

## 今後のルール
- NotebookLMで重要な発見があったら、MrBrainへ保存する。
- NotebookLMを保存庫にしない。
- NotebookLMのチャット履歴に依存しない。
- 残したいことは、必ずMrBrainのMarkdownにする。

## AI導入ログ
```md
2026-06-23
最初はNotebookLMを記憶装置だと思っていた。
しかし実際は、ソースに質問するための知識検索AIとして扱うのがよいと理解した。
保存先はMrBrainにする。
```

## MrBrainへの影響
MrBrainは、AIツールで得た気づきの最終保存先である。

NotebookLM、ChatGPT、Codex、Browser、Google Driveなど、どのツールで得た情報でも、残したいものはMrBrainへ整理して保存する。
