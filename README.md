# iChoosr 日本版ブランドガイドライン｜Web版

`Switch Together — Brand Guidelines, Japan Edition`

iChoosr Japan のブランドガイドラインの Web 版です。本国 Brand Guidelines を、WS01-03＋ミニWS01（2026/5/19）の議論を経て日本市場向けにチューニングした、運用前提の統合ガイドラインです。

---

## 構成

```
web/
├── index.html                    # ホーム（ナビ）
├── assets/style.css              # 共通スタイル
├── favicon.svg / og-image.svg    # メタ情報用画像
├── robots.txt                    # 検索エンジン除外設定
├── guidelines/                   # 本体ガイドライン（9セクション）
│   ├── 01-brand-proposition.html
│   ├── 02-customer-value-proposition.html
│   ├── 03-customer-value-pillars.html
│   ├── 04-brand-personality.html
│   ├── 05-brand-promise.html
│   ├── 06-brand-story.html
│   ├── 07-brand-values.html
│   ├── 08-tone-of-voice.html
│   └── 09-key-message-hierarchy.html
└── operations/                   # 運用ガイドライン（4章）
    ├── 01-ng-list.html
    ├── 02-before-after.html
    ├── 03-checklist.html
    └── 04-methodology.html
```

## 技術スタック

- 純粋な HTML + CSS のみ（JavaScript 不使用）
- 外部CDN・外部フォント不使用（システムフォント完結）
- 静的ファイルのみ。任意のホスティングで動作

## 公開ポリシー

- **検索エンジン除外**：全ページに `<meta name="robots" content="noindex,nofollow">`、`robots.txt` で全クロール拒否
- **アクセス制限**：URLを知る人のみ閲覧可能
- **機密情報**：内部評価値・参加者名・WSスコアを含むため、URLの取り扱いには注意

---

## ローカルで開く

```bash
cd web
python3 -m http.server 8090
# → http://localhost:8090/
```

---

## デプロイ手順

### 選択肢A：GitHub Pages（最も簡単・無料）

1. GitHub で新規リポジトリを作る（例: `ichoosr-brand-guidelines`）
   - **Private リポジトリでもPages公開可（Pro/Team プラン）。Freeなら Public 必須**
2. このディレクトリを push
   ```bash
   cd web
   git init
   git add .
   git commit -m "Initial publish"
   git branch -M main
   git remote add origin https://github.com/<your-account>/ichoosr-brand-guidelines.git
   git push -u origin main
   ```
3. GitHub の Settings → Pages で `Deploy from a branch` → `main` / `/ (root)` を選択
4. 数分後、`https://<your-account>.github.io/ichoosr-brand-guidelines/` でアクセス可能

### 選択肢B：Netlify（パスワード保護したい場合）

1. Netlify アカウント作成
2. このディレクトリを drag & drop で deploy（CLI不要）
3. Site settings → Visitor access → Password protection でパスワード設定（Pro plan）

### 選択肢C：Vercel

1. Vercel アカウント作成
2. GitHub 連携または CLI で deploy
3. Settings → Deployment Protection でパスワード保護可（Pro plan）

### 選択肢D：Cloudflare Pages

1. Cloudflare アカウント作成
2. GitHub 連携でリポジトリを指定 / 直接 `wrangler` CLI で deploy
3. Cloudflare Access でアクセス制限可能（Free plan も対応）

---

## 更新サイクル

- 本体（guidelines/）：原則として年単位で見直し（毎年5月、本国 fy 切替に合わせる）
- 運用補助（operations/）：月次で運用ログ蓄積、四半期で追記更新
- 改訂時は `git commit` → `git push` で自動デプロイ（GitHub Pages / Netlify / Vercel いずれも）

---

## 関連ドキュメント

- 本体（Word版）：`../iChoosr日本版ブランドガイドライン.docx`
- 運用版（Word版）：`../iChoosr日本版ブランド運用ガイドライン.docx`
- 議論の根拠：`../これまでの議論_全体要点整理.docx`
- 本国原文：`../本国ブランドガイドライン_英日併記版.docx`
- 全体INDEX：`../INDEX.md`

---

最終更新：2026-05-22（ミニWS01反映版）
