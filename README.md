# e-create-web

株式会社イークリエイトのコーポレートサイト。  
Astro + Tailwind CSS で構築し、Cloudflare Pages でホスティング。

---

## 技術スタック

| 項目 | 内容 |
| :--- | :--- |
| フレームワーク | [Astro](https://astro.build/) v6 |
| CSSフレームワーク | [Tailwind CSS](https://tailwindcss.com/) v4 |
| CMS | [microCMS](https://microcms.io/) |
| ホスティング | [Cloudflare Pages](https://pages.cloudflare.com/) |
| Node.js | >= 22.12.0 |

---

## ブランチ構成

```
main        ← 公開用（本番環境）
  ↑ 問題なければマージ
test        ← テスト用（Staging環境）
  ↑ 機能完成したらマージ
develop     ← 開発用（日々の作業）
```

| ブランチ | 用途 |
| :--- | :--- |
| `main` | 本番公開用。このブランチへのマージが本番反映のトリガー |
| `test` | ステージング確認用。動作確認後に main へマージ |
| `develop` | 日々の開発作業ブランチ |

---

## 自動デプロイ

以下のいずれかをトリガーに Cloudflare Pages が自動ビルド・デプロイされる。

- **GitHub `main` ブランチへのマージ** → Webhook で Cloudflare Pages をビルド
- **microCMS のコンテンツ更新** → Webhook で Cloudflare Pages をビルド

---

## ローカル開発

```bash
# 依存パッケージのインストール
npm install

# 開発サーバー起動（http://localhost:4321）
npm run dev

# 本番ビルド
npm run build

# ビルド後のプレビュー
npm run preview
```

---

## バージョン管理

リリースごとに git タグを付与して管理。詳細な変更履歴は [CHANGELOG.md](CHANGELOG.md) を参照。

```bash
# タグ一覧
git tag --sort=-version:refname

# タグ間のコード差分を確認
git diff v1.0.0 v1.0.1

# タグ間のコミット一覧を確認（1行表示）
git log v1.0.0..v1.0.1 --oneline
```

---

## ディレクトリ構成

```
/
├── public/
│   └── assets/         # 画像・静的ファイル
├── src/
│   ├── components/     # 各セクションのAstroコンポーネント
│   ├── layouts/        # 共通レイアウト
│   ├── pages/          # ルーティング（.astroファイル）
│   └── styles/         # CSSファイル
├── astro.config.mjs
└── package.json
```
