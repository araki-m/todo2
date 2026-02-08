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
- フィルター: すべて / 未完了 / 完了 のステータスフィルターと、全カテゴリ / 仕事 / プライベート / その他 のカテゴリフィルターを組み合わせ可能（状態はLocalStorageに保存しない）
- ステータスバー: タイトル下に完了(青)/未完了(オレンジ)の棒グラフと件数を表示
- ページタブ: 「TODO」「分析」「データ」タブの切り替え
- 分析タブ: 概要（合計/完了/未完了）、カテゴリ別完了率、締切状況（期限切れ/2日以内/余裕あり）、完了数の時系列線グラフ（全体+カテゴリ別、Canvas描画）を表示
- 完了日記録: チェック時に `completedAt` を記録（既存データは `createdAt` にフォールバック）
- 並び替え: ドラッグ＆ドロップでタスクの順番を変更可能（HTML5 Drag and Drop API使用、配列順序で管理）
- データタブ: エクスポート（JSONダウンロード）/ インポート（JSONファイル読み込み、バリデーション付き）
- 注意: Canvas描画は分析タブ表示時に実行（`display:none` 中はサイズ取得不可のため）

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
      "deadline": "2026-02-10",
      "completedAt": null
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
