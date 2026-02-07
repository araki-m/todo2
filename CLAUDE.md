# TODO App

LocalStorageを使ったシンプルなTODOアプリ。

## 構成

- `index.html` — HTML/CSS/JS を1ファイルに統合したSPA

## 技術仕様

- フレームワーク不使用（Vanilla JS）
- データ永続化: LocalStorage（キー: `todo-app-data`）
- 各TODOにはNo.（自動採番、欠番許容）が付与される

## データ構造

```json
{
  "nextNo": 3,
  "todos": [
    { "no": 1, "text": "タスク内容", "done": false }
  ]
}
```

## 開発環境

- プラットフォーム: Cygwin on Windows
- ビルドツール不要。ブラウザで `index.html` を直接開いて動作確認する
