# FE-BrainLab | 基本情報アクティブリコール道場

最新の認知科学・実証的記憶術（アクティブリコール、分散学習、ファインマン・テクニック、耳学）を取り入れた、基本情報技術者試験（FE）特化型の自作学習Webアプリケーションです。

---

## 🎯 開発の目的と戦略
1. **AIバイブコーディング × 資格学習の二重取り**:
   - 受動的に問題を解くのではなく、「出題・解説・視覚化ツールを開発する側」に回ることで、メタ認知（プロテジェ効果）を発動させ記憶定着率を最大化。
2. **科目A（午前）対策**:
   - シラバス改訂に伴う最新用語（生成AI、ゼロトラスト、コンテナ、CDN等）を「日常のたとえ話」と紐付けてアクティブリコール。
3. **科目B（午後）対策**:
   - VBA経験者の強みを活かしつつ、「頭の中だけで追ってパンクする」ワーキングメモリの過負荷を解消するトレース表ビジュアライザーを搭載。
4. **スキマ時間活用**:
   - 通勤15分で画面を見ずに用語解説を聞き流せる「自動オーディオブック（耳学）」モード。

---

## 🚀 Cloudflare Pages へのデプロイ手順（GitHub自動連携）

本アプリは単一の静的HTML（Tailwind CDN / Web Speech API）で構築されているため、Node.js等の複雑なビルド処理は不要です。Cloudflare Pagesの無料プランで全世界のCDNから超高速配信されます。

### Step 1: GitHubにリポジトリを作成
1. GitHubにログインし、新しいリポジトリ（例: `AntigravityFE` または `fe-brainlab`）を作成（PublicまたはPrivateどちらでも可）。
2. ローカルからプッシュ:
   ```bash
   git add .
   git commit -m "feat: initial prototype of FE-BrainLab"
   git branch -M main
   git remote add origin https://github.com/<あなたのユーザー名>/<リポジトリ名>.git
   git push -u origin main
   ```

### Step 2: Cloudflare Pagesと連携
1. [Cloudflare ダッシュボード](https://dash.cloudflare.com/) にログイン。
2. 左メニュー **「Workers & Pages」** > **「Create application」** > **「Pages」** > **「Connect to Git」** を選択。
3. 作成したGitHubリポジトリを選択。
4. ビルド設定:
   - **Framework preset**: `None`
   - **Build command**: （空欄）
   - **Build output directory**: `/` （または空欄）
5. **「Save and Deploy」** をクリック！
6. 数十秒で専用URL（例: `https://fe-brainlab.pages.dev`）が発行され、スマホからアクセス可能になります。
7. 以降は、コードを変更して `git push` するだけで自動的に全世界に反映されます。
