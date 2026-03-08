# Reading App 設計メモ

読書ログリポジトリ `reading-archive` をデータソースとして  
Flutter + C# で読書アプリを作る練習プロジェクト。

## 目的

- Flutter開発の練習
- API連携の理解
- 業務で行っている設計の再現
- 自分の読書ログの可視化
- ポートフォリオとして残す

---

# 全体構成

```text
projects
├ reading-archive # 読書ログ（Markdown DB）
└ reading-app # アプリ
```

---

# アーキテクチャ

```text
Flutter (フロント)
↓ API
C# (.NET backend)
↓
Reading Archive (Markdown)
```

## 役割

### Flutter
- 画面表示
- API呼び出し
- 状態管理

### C# API
- 読書データ取得
- JSONとして返却

### reading-archive
- 読書ログ
- Markdown + YAML frontmatter
- 簡易DBとして扱う

---

# 開発ステップ

## Step1 Flutterのみ

まず画面だけ作る。

機能

- 本一覧画面
- 本詳細画面

データはコード内のダミーデータ。

---

## Step2 JSONデータ化

読書データをJSONとして扱う。

学習内容

- モデルクラス
- JSONパース
- 非同期データ読み込み

---

## Step3 C# API作成

.NETでAPIを作る。

例


GET /books
GET /books/{id}


役割

- 読書データを取得
- JSONとして返す

---

## Step4 Flutter → API接続

FlutterからAPIを呼ぶ。

技術

- Dio
- Repositoryパターン
- 状態管理

---

# 最初に作る画面

アプリは以下の3画面に絞る。

## 本一覧

表示

- タイトル
- 著者
- 読了日

---

## 本詳細

表示

- summary
- impression
- quotes

---

## 検索

検索条件

- タイトル
- 著者
- タグ

---

# このプロジェクトの価値

単なる練習ではなく

- データ設計
- API設計
- フロント実装

を一通り経験できる。

また、自分の読書ログを使うため  
実データを扱うポートフォリオになる。

---

# 将来的にやりたいこと

- タグ検索
- 読書統計
- 著者別一覧
- 国別文学
- 年間読書グラフ

---

# 保存場所


reading-app
└ docs
└ architecture.md


または


reading-app
└ notes
└ plan.md
