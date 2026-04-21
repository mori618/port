# My Works - ポートフォリオサイト

自身が作成したゲーム・Webサービスなどの制作物を一覧表示するポートフォリオサイトです。

## 📁 ディレクトリ構成

```
portfolio/
├── index.html          # 一覧ページ（React + Tailwind CSS）
├── projects.json       # 制作物データ（一覧ページが読み込む）
├── images/             # サムネイル画像フォルダ
│   └── *.jpg / *.png
└── projects/           # 各制作物の詳細ページ
    ├── puzzle-rogue.html
    ├── task-manager.html
    └── ...
```

## 🚀 GitHub Pagesへの公開手順

1. GitHubリポジトリを作成（例: `[ユーザー名].github.io`）
2. `portfolio/` フォルダの中身をリポジトリのルートに配置
3. リポジトリの Settings > Pages > Source を `main` ブランチに設定
4. `https://[ユーザー名].github.io/` でアクセス可能になります

## ✏️ 新しい制作物の追加方法

### 1. `projects.json` にデータを追記する

```json
{
  "id": "my-new-work",
  "title": "新しい制作物のタイトル",
  "category": "game",  // "game" or "webservice" など
  "description_short": "一覧カードに表示する短い説明文。",
  "thumbnail": "./images/my-new-work-thumb.jpg",
  "detail_url": "./projects/my-new-work.html",
  "tags": ["ゲーム", "JavaScript"],
  "created_at": "2024-12-01"
}
```

### 2. サムネイル画像を `images/` フォルダに配置する

推奨サイズ: **横 600px × 縦 400px**（3:2 比率）

### 3. 詳細ページを `projects/` に作成する

`projects/puzzle-rogue.html` を**コピーして**、以下を変更してください：
- `<title>` タグ
- OGP metaタグ（`og:title`, `og:description`, `og:image`）
- `<h1>` タグ（制作物名）
- メタ情報（制作日、更新日）
- タグ一覧
- メイン画像の `src` と `alt`
- 説明文
- 使用技術一覧
- アクションボタンの `href`（実際のURLに変更）

## 🎨 デザイン仕様

| 項目 | 内容 |
|------|------|
| テーマ | OS設定に合わせてライト/ダーク自動切り替え |
| アクセントカラー | `#6C63FF`（パープル系） |
| フォント | Noto Sans JP + Inter |
| レスポンシブ | スマホ〜PC対応（Tailwind CSS） |
| フィルター方式 | タグのAND検索（複数選択） |
| ソート | 新しい順 / 古い順 / 名前順 |

## 💡 Google AdSense 導入時

`index.html` と各詳細ページのコメントアウト部分 `<!-- 広告枠 -->` を解除し、
AdSenseのコードを貼り付けてください。

```html
<!-- 広告枠がある場所 -->
<!-- <div class="mb-8 text-center">
  ここにGoogle AdSense コードを挿入
</div> -->
```

## 🔧 ローカルでの動作確認

`fetch` APIでJSONを読み込むため、ファイルをブラウザで直接開くと
CORSエラーになる場合があります。以下の方法でローカルサーバーを起動してください：

```bash
# Python 3
cd portfolio
python3 -m http.server 8000
# → http://localhost:8000 でアクセス
```

または VSCode の **Live Server** 拡張機能を利用してください。
