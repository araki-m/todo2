# TODO App

LocalStorageを使ったシンプルなTODOアプリ。

## 構成

- `index.html` — HTML/CSS/JS を1ファイルに統合したSPA

## 技術仕様

- フレームワーク不使用（Vanilla JS）
- データ永続化: LocalStorage（キー: `todo-app-data`）
- 各TODOにはNo.（自動採番、欠番許容）が付与される
- カテゴリ: 仕事(`work`) / プライベート(`private`) / その他(`other`) を選択可能
- 登録日付: TODO追加時に自動記録
- 締め切り日: 任意で設定可能。締切2日以内の未完了TODOは赤枠で強調表示
- フィルター: すべて / 未完了 / 完了 のタブ切り替え表示（状態はLocalStorageに保存しない）

## データ構造

```json
{
  "nextNo": 3,
  "todos": [
    {
      "no": 1,
      "text": "タスク内容",
      "done": false,
      "createdAt": "2026-02-07",
      "category": "work",
      "deadline": "2026-02-10"
    }
  ]
}
```

## デプロイ

- GitHub Pages: `main` ブランチへのpushで自動デプロイ（`.github/workflows/pages.yml`）
- URL: https://araki-m.github.io/todo2/

## 開発環境

- プラットフォーム: Cygwin on Windows
- ビルドツール不要。ブラウザで `index.html` を直接開いて動作確認する
