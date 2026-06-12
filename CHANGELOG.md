# CHANGELOG

このプロジェクトのバージョンごとの変更履歴。

---

## [v1.0.1]

### 修正
- **日付のタイムゾーンずれを修正**（`Hero.astro` / `Special.astro` / `events/index.astro`）  
  - `toLocaleDateString("ja-JP")` に `{ timeZone: "Asia/Tokyo" }` を追加
  - microCMSの日付がUTC基準で解釈され1日前に表示される問題を解消

### 追加
- **ヘッダーロゴを画像に差し替え**（`Layout.astro`）  
  - テキストベースの社名表示 → `logo_full.png`（透過PNG）に変更
  - ヘッダー余白・ロゴサイズを調整

---

## [v1.1.0]

### 追加
- 感染対策ページ用の画像5枚を追加（`public/assets/infection_images/`）
- イベント一覧JS（`public/assets/js/events-list.js`）を新規追加（84行）
- `gallery.css` を新規追加（ギャラリーレイアウト用スタイル 95行）

### 変更
- **イベント機能を大幅強化**（`public/assets/js/event.js`）  
  - タグフィルタリング、ページネーション、モーダル表示など機能拡充
- **CSS設計を共通ユーティリティクラスに統一**（`src/styles/common.css` に426行追加）  
  - `section-container` / `section-eyebrow` / `section-title` / `section-divider` 等のセクション共通クラスを定義
  - `btn-primary` / `btn-transparent` / `card--detail` / `checklist-item` 等のUIクラスを定義
- **全コンポーネントのインラインTailwindを共通クラスへ置き換え**  
  - 対象：`About` / `Access` / `Company` / `Contact` / `Hero` / `Recruit` / `Service` / `Special` / `Strength` / `Workflow` / `Works` / `Layout`
- 感染対策ページ（`src/pages/infection.astro`）の内容を大幅改修
- イベント一覧ページ（`src/pages/events/index.astro`）を整理・簡素化
- イベント詳細ページ（`src/pages/events/[id].astro`）のレイアウトを改修

### 規模
- 変更ファイル数：25ファイル
- 追加：1,189行 / 削除：517行

---

## [v1.0.0]

### 追加
- サービス01の画像をローカルファイルに移行（`public/assets/images/service1-unsplash.jpg`）

### 変更
- **会社情報の更新**（`Company.astro`）  
  - 従業員数：11名（2022年7月現在）→ 17名（2026年4月現在）
- **サービス画像を外部URLからローカル参照に変更**（`Service.astro`）  
  - Unsplash外部リンク → `/assets/images/service1-unsplash.jpg`
- **ご依頼の流れのステップ順序・文言を修正**（`Workflow.astro`）  
  - 「設計・お見積り」→「お見積り・設計」
  - 「納品・動作試験」→「動作試験・納品」
  - 各ステップの説明文を微調整、インデント整形
- **ナビゲーションメニューの整理**（`Layout.astro`）  
  - 「事業内容トップ」→「事業内容」に改称
  - 「特設セクション」→「特設・イベント」に改称
  - 「実績一覧」「リニア駅建設」のリンクをコメントアウト（非表示化）
- **イベントのお知らせ文言を修正**（`Special.astro`）  
  - 「社内行事や記念イベントの様子を公開しています。」  
  → 「会社からのお知らせをはじめ、社内イベントの様子などを随時公開しています。」
- **「イベント一覧に戻る」リンク先を変更**（`events/[id].astro`）  
  - `/#special` → `/events`
- Works カードの `cursor-pointer` を削除（`Works.astro`）

### 規模
- 変更ファイル数：8ファイル
- 追加：32行 / 削除：26行

---

## [v0.9.0]

初期リリース。
