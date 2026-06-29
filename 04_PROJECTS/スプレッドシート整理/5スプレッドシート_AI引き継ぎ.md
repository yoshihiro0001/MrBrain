# 5スプレッドシート AI引き継ぎ

## 目的
他のAIやCodexが、5つのGoogleスプレッドシートを見たときに、すぐ目的・読む順番・会社マスターの場所を理解できるようにする。

このファイルは中身の丸写しではなく、安全な索引である。

## 重要な前提
Google Driveに接続できるAIは、下記URLからシート本文を読める。

Google Driveに接続できないAIは、URLだけでは中身を読めない。
その場合は、このMrBrain内の索引・現状分析・会社マスター索引を読ませる。

## 5つの正本候補
| No | スプレッドシート | 役割 | 最初に読むタブ | 注意 |
|---|---|---|---|---|
| 1 | 家族・法人_契約状況及び資産記録一元管理シート | 家族・法人の契約、固定費、保険、医療、人/法人マスター | `総合ダッシュボード` / `00_Master_Plan` | 生活・法人情報が混在 |
| 2 | JOY | ホテルJOYの運営台帳 | `会社情報` / `集計` / `売上` / `経費入力` | ID・パスワード列があるため扱い注意 |
| 3 | 孝行_操作システム_アプリ連携版 | アプリ連携、承認、仕訳、スタッフ権限の操作レイヤー | `0.1_開発ステータス` / `01_マスタ` / `0.2_アプリ画面設計` | 開発仕様と業務データが混在 |
| 4 | 孝行_第40期申告システム_確定 | 第40期の申告成果物 | `00_引き継ぎ` / `02_会社マスタ` / `14_eTax転記ガイド` | 確定版。原本扱い |
| 5 | 孝行_申告システム_汎用版2 | 汎用申告エンジン | `00_はじめに` / `01_マスタ` / `0.1_開発ステータス` | 今後の申告システムの土台 |

## URLとID
| No | スプレッドシートID | URL |
|---|---|---|
| 1 | `1VtI7xEGnxpw4vPLFh9jokyPPmnBtg8eAGdlUw8LrbTo` | https://docs.google.com/spreadsheets/d/1VtI7xEGnxpw4vPLFh9jokyPPmnBtg8eAGdlUw8LrbTo/edit |
| 2 | `1TKSekkcmNZHvPnTiKeE3ZTkyC-dFBgMu0HrSvJ12EBQ` | https://docs.google.com/spreadsheets/d/1TKSekkcmNZHvPnTiKeE3ZTkyC-dFBgMu0HrSvJ12EBQ/edit |
| 3 | `1ZQ8t4X4M97s4NvgKb6g7TsDUc3nP4_jNefp5S8MPmLs` | https://docs.google.com/spreadsheets/d/1ZQ8t4X4M97s4NvgKb6g7TsDUc3nP4_jNefp5S8MPmLs/edit |
| 4 | `1ytvbFCCk6z8dU51HK_W2fdQ-fWub7drwMV7q6unCWcA` | https://docs.google.com/spreadsheets/d/1ytvbFCCk6z8dU51HK_W2fdQ-fWub7drwMV7q6unCWcA/edit |
| 5 | `1NXlMMAXqNJVWM7Ex_Ew3FYmnxJQbPDbl-Q8Pj_Z7F4g` | https://docs.google.com/spreadsheets/d/1NXlMMAXqNJVWM7Ex_Ew3FYmnxJQbPDbl-Q8Pj_Z7F4g/edit |

## シート別の読み方

### 1. 家族・法人_契約状況及び資産記録一元管理シート
目的:
- 家族・法人の固定費、保険、医療費、契約、マスターを集約する。

読む順番:
1. `総合ダッシュボード`
2. `00_Master_Plan`
3. `01_Human_Master`
4. `02_Entity_Master`
5. `固定費・インフラ契約`
6. `保険・共済契約`

会社マスター:
- `02_Entity_Master`

人マスター:
- `01_Human_Master`

MrBrain上の関係:
- [[02_LIFE/契約一覧]]
- [[03_BUSINESS/契約/README]]
- [[03_BUSINESS/会社マスター索引]]

### 2. JOY
目的:
- ホテルJOYの運営を一括管理する。
- 売上、経費、人件費、設備、固定費、税金、取引先、口コミ、Booking文面まで含む。

読む順番:
1. `会社情報`
2. `集計`
3. `売上`
4. `経費入力`
5. `人件費`
6. `設備・消耗品`
7. `取引先情報`
8. `固定費`

会社マスター:
- `会社情報`

注意:
- `ID`、`パスワード`、`契約番号`、`メールアドレス` などの列がある。
- AIに渡す場合は、必要な列だけに絞る。

MrBrain上の関係:
- [[03_BUSINESS/JOY/README]]
- [[03_BUSINESS/経理/README]]
- [[03_BUSINESS/スタッフ/README]]
- [[03_BUSINESS/設備/README]]
- [[04_PROJECTS/ホテルシステム/README]]

### 3. 孝行_操作システム_アプリ連携版
目的:
- アプリから受けた入力を確認・承認し、仕訳帳へつなぐ操作レイヤー。
- スタッフ、権限、科目変換、アプリ画面設計を含む。

読む順番:
1. `0.1_開発ステータス`
2. `01_マスタ`
3. `0.2_アプリ画面設計`
4. `01.1_科目変換マスタ`
5. `01.2_スタッフマスタ`
6. `01.3_権限マスタ`
7. `11_アプリ連携受取`
8. `02_仕訳帳`

会社マスター:
- `01_マスタ`

MrBrain上の関係:
- [[04_PROJECTS/経理アプリ/ACCOUNTING_APP_PLAN]]
- [[04_PROJECTS/申告システム/README]]
- [[03_BUSINESS/孝行/README]]
- [[03_BUSINESS/スタッフ/README]]

### 4. 孝行_第40期申告システム_確定
目的:
- 孝行の第40期申告を完成させた確定版。
- 申告時の証跡、入力、PL、BS、消費税、e-Tax転記ガイドを含む。

読む順番:
1. `00_引き継ぎ`
2. `02_会社マスタ`
3. `04_売上入力`
4. `05_経費入力`
5. `07_PL`
6. `08_BS`
7. `09_消費税`
8. `14_eTax転記ガイド`

会社マスター:
- `02_会社マスタ`
- `00_引き継ぎ` にも重要な会社基本情報と申告前提がある。

注意:
- 確定版なので、勝手に編集しない。
- 税務判断や提出済み情報を含むため原本扱い。

MrBrain上の関係:
- [[03_BUSINESS/孝行/README]]
- [[03_BUSINESS/税務/README]]
- [[04_PROJECTS/申告システム/README]]

### 5. 孝行_申告システム_汎用版2
目的:
- 第40期申告システムを汎用化し、別会社や翌期にも使えるようにした申告エンジン。
- 仕訳帳、PL、BS、固定資産、転写ガイド、検算、翌期引継を含む。

読む順番:
1. `00_はじめに`
2. `01_マスタ`
3. `0.1_開発ステータス`
4. `02_仕訳帳`
5. `11_アプリ連携受取`
6. `04_PL`
7. `05_BS`
8. `06_固定資産`
9. `08_転写ガイド`
10. `09_検算`

会社マスター:
- `01_マスタ`

MrBrain上の関係:
- [[04_PROJECTS/申告システム/README]]
- [[04_PROJECTS/経理アプリ/ACCOUNTING_APP_PLAN]]
- [[03_BUSINESS/税務/README]]

## 他AIに渡すときの短い説明
```md
この5つのGoogle Sheetsは、JOY運営、孝行の申告、経理入力、契約・保険・医療・会社マスターを管理している。
まずMrBrainの `04_PROJECTS/スプレッドシート整理/5スプレッドシート_AI引き継ぎ.md` と `03_BUSINESS/会社マスター索引.md` を読む。
Google Driveに接続できる場合は、各シートの「最初に読むタブ」から確認する。
Google Driveに接続できない場合は、MrBrain内の索引と現状分析だけを使う。
税務・契約・個人情報は原本扱いし、全文を外部に貼らない。
```

## 関連ファイル
- [[04_PROJECTS/スプレッドシート整理/SPREADSHEET_INDEX]]
- [[04_PROJECTS/スプレッドシート整理/現状分析_5スプレッドシート_2026-06-22]]
- [[03_BUSINESS/会社マスター索引]]
