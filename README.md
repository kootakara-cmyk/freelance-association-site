# Freelance-Association.Org — Archive Site

日本フリーランス協会（Japan Freelance Association）の活動記録アーカイブサイト。
2008年の設立から現在に至る組織の変遷を、一次資料（旧公式サイトのアーカイブ）と
関係者提供情報を出典区分した上で記録する、静的サイトです。

Archive site recording the history of the Japan Freelance Association,
from its founding in 2008 to the present. Primary-source archive records
and supplemental information from related parties are clearly distinguished
throughout.

---

## 構成 / Structure

```
.
├── index.html          # サイト本体（単一ファイル、HTML+CSS+JS）
├── archive_data.json   # 旧公式サイト（2009–2022運用）からのテキストアーカイブ
├── wrangler.jsonc      # Cloudflare Workers デプロイ・ルーティング設定
├── README.md           # 本ファイル
├── LICENSE             # ライセンス
├── .gitignore
└── _headers            # セキュリティヘッダー設定
```

`index.html` は外部ビルドツールに依存しない単一ファイル構成です。
`archive_data.json` を同一ディレクトリに配置することで、サイト内の
「Open Archive／アーカイブを開く」ボタンから旧サイト記録を閲覧できます。

## 稼働状況 / Deployment Status

- ドメイン：`freelance-association.org`（Cloudflare Registrar へ移管完了・アクティブ）
- ネームサーバー：`adelaide.ns.cloudflare.com` / `fattouche.ns.cloudflare.com`
- ホスティング：Cloudflare Workers（本リポジトリと連携、静的アセット配信）
- メール：Cloudflare Email Routing（キャッチオール有効、単一Gmail宛に集約）

## 技術仕様 / Technical Notes

- 静的サイト（ビルド不要）。Cloudflare Workers 静的アセット配信で動作します。
- 外部依存：Google Fonts（Noto Serif JP, Noto Sans JP, EB Garamond, Inter, JetBrains Mono）
- JavaScript：バニラJS のみ（フレームワーク非依存）。折りたたみ表示に `<details>` 要素を使用。
- 言語：英語を第一言語、日本語を第二言語として併記。第三言語は外部翻訳サービス（Google翻訳）への導線を提供。

## 出典区分について / Source Attribution

サイト内の記述は以下の2種に区分されています。

- **Archive Record（アーカイブ記載）**：2009〜2022年運用の旧公式サイト（BiND形式バックアップ）本文に
  実在するテキストに基づく記述。`archive_data.json` 内のデータが該当します。
- **Related Party / Supplemental（関係者提供情報）**：旧サイトの記述にはない、関係者からの
  口頭・追加提供による補足情報。本文中に出典タグで明示しています。

## デプロイ / Deployment

本リポジトリは Cloudflare Workers（静的アセット配信）との連携を前提としています。
`wrangler.jsonc` にルーティング設定を含みます。詳細な手順は運用ガイド
（別途配布）を参照してください。概要は以下の通りです。

1. 本リポジトリを GitHub にプッシュ
2. Cloudflare Workers & Pages で本リポジトリと連携（デプロイコマンド：`npx wrangler deploy`）
3. `wrangler.jsonc` の `routes` 設定により、`freelance-association.org` へ自動的に紐づく
   （前提：ドメインのレジストラ移管・ネームサーバー設定が完了していること）

## ライセンス / License

サイトコード（HTML/CSS/JS）は MIT License の下で公開します。
`archive_data.json` に含まれる旧サイトのテキストは、団体自身のアーカイブ記録として
掲載するものであり、再配布・二次利用については別途お問い合わせください。

---

*This is an archival record. It does not accept inquiries or link to external member services.*
*本サイトはアーカイブ記録です。問合せ対応や外部会員サービスへの導線は含みません。*
