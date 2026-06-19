# 000-hub（ツール置き場 公式トップ）

`https://ai-kaihatsubu.github.io/`（組織ルート）に配信される、ツール置き場の全ツールへのリンク集ハブ。
AdSense審査用のホームページとして、プライバシーポリシー・利用規約・運営者情報・ads.txt等を備える。

## 構成

| ファイル | 役割 |
| --- | --- |
| `index.html` | ブランド公式トップ。全11ツール＋オールインワン版へのリンクカード、サイト紹介、AdSense検証タグ差込口を含む。 |
| `style.css` | カードグリッド・レスポンシブ・ダーク/ライト切替対応のCSS（CSS変数管理、外部CDN不使用）。 |
| `app.js` | ダーク/ライト切替（localStorage保存）。 |
| `manifest.webmanifest` / `sw.js` / `icons/` | PWA対応（オフラインキャッシュ、ホーム画面追加）。`CACHE_NAME="hub-v1"`。 |
| `ads.txt` | Google AdSense用。`pub-XXXXXXXXXXXXXXXX`はTODO（承認後に実publisher IDへ差し替え）。 |
| `privacy.html` | プライバシーポリシー（AdSense・Cookie・オプトアウト方法を記載）。 |
| `terms.html` | 利用規約。 |
| `operator.html` | 運営者情報（社長記入のTODOあり）。 |

## AdSense申請手順

1. このサイト（`ai-kaihatsubu.github.io`、本ハブ含む各ツール）を公開する。
2. Google AdSenseの管理画面で「サイトを追加」から `ai-kaihatsubu.github.io` を登録する。
3. 表示される検証用 `<script>` タグを、`index.html` 内の以下のプレースホルダ部分に貼り付ける。

   ```html
   <!-- ▼▼ AdSense検証タグをここに貼る（AdSense管理画面の「サイトを追加」で表示される <script async src="...adsbygoogle.js?client=ca-pub-XXXX"...></script> を貼り付け） ▼▼ -->
   <!-- ▲▲ ここまで ▲▲ -->
   ```

4. `ads.txt` の `pub-XXXXXXXXXXXXXXXX` を、AdSenseで発行された実際のpublisher IDに差し替える。
5. 審査を待つ（反映には数日〜数週間かかる場合がある）。

## 運営者情報の記入

`operator.html` 内のTODO（運営者名・連絡先）を記入すること。有料機能（Stripe課金等）を導入する場合は、特定商取引法に基づく表記の追記が必要。
