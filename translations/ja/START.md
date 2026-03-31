The user wants me to translate a Markdown document from zh-CN (Simplified Chinese) to ja (Japanese). I need to:

1. Preserve all Markdown formatting
2. NOT translate code snippets, variable names, function names, or technical identifiers
3. NOT translate URLs, file paths, or command-line examples
4. Preserve the original document structure
5. Maintain a professional and accurate translation tone
6. Keep inline code (`code`) untranslated
7. Translate comments in code blocks if they are in the source language
8. Preserve all HTML tags and their attributes
9. Keep emojis and special characters as-is
10. Do NOT add any explanations or notes

Let me translate this document carefully:

Title: # 🚀 GitHub Global - 立即开始
Translation: # 🚀 GitHub Global - 今すぐ始める

Section: ## 最快启动方式 (3 步)
Translation: ## 最も 빠른起動方法 (3ステップ)

And so on...

I need to be careful about:
- Code blocks - keep as-is
- URLs - keep as-is
- File paths - keep as-is
- Variable names like DATABASE_URL, NEXTAUTH_URL, etc. - keep as-is
- Technical terms that are commonly used in English in Japanese tech context

Let me start translating:
</think>

# 🚀 GitHub Global - 今すぐ始める

## 最も速い起動方法 (3ステップ)

### 1️⃣ 依存関係のインストール

```bash
npm install
```

### 2️⃣ 環境変数の設定

`.env` ファイルを作成:

```bash
# サンプルファイルをコピー
cp .env.example .env
```

**最小設定** (必須):

```env
# データベース
DATABASE_URL="mysql://root:password@localhost:3306/github_global"

# NextAuth
NEXTAUTH_URL="http://localhost:3000"
NEXTAUTH_SECRET="your-random-secret"

# 暗号化キー
ENCRYPTION_KEY="your-32-byte-hex-key"

# GitHub App (作成後に記入)
GITHUB_APP_ID="your-app-id"
GITHUB_APP_CLIENT_ID="your-client-id"
GITHUB_APP_CLIENT_SECRET="your-client-secret"
GITHUB_APP_PRIVATE_KEY="your-private-key"
```

**キーの生成**:

```bash
# NEXTAUTH_SECRET
openssl rand -base64 32

# ENCRYPTION_KEY
node -e "console.log(require('crypto').randomBytes(32).toString('hex'))"
```

**GitHub App の作成**: https://github.com/settings/apps/new にアクセス

### 3️⃣ 初期化して起動

```bash
# Prisma Client を生成
npm run db:generate

# データベースを初期化
npm run db:push

# 開発サーバーを起動
npm run dev
```

アクセス先: **http://localhost:3000**

---

## 🎯 機能特徴

✅ **実装済みの機能**:

- ✨ ホーム画面と製品紹介
- 🔐 GitHub OAuth ログイン (NextAuth.js)
- 📊 ダッシュボード - リポジトリリスト管理
- 🗂️ リポジトリ詳細 - 翻訳タスクの表示
- ⚙️ 翻訳設定 - 言語とファイル範囲の選択
- 🔧 設定ページ - API Key 管理
- 🗄️ データベース設計 (Prisma + MySQL)
- 🎨 中国赤テーマ UI (Tailwind CSS)
- 📱 レスポンシブデザイン

🚧 **未実装の機能** (バックエンド統合が必要):

- GitHub API 統合
- OpenRouter AI 翻訳
- 翻訳タスクキュー
- リアルタイム進捗表示 (SSE)
- PR 自動作成

---

## 📁 プロジェクト構造

```
github-global/
├── src/
│   ├── app/                      # Next.js ページ
│   │   ├── page.tsx             # ホーム画面
│   │   ├── dashboard/           # ダッシュボード
│   │   ├── repo/[id]/           # リポジトリ詳細
│   │   │   ├── page.tsx         # リポジトリ主页
│   │   │   └── config/          # 翻訳設定
│   │   ├── settings/            # 設定ページ
│   │   └── api/                 # API ルート
│   ├── components/ui/           # UI コンポーネント
│   ├── lib/                     # ユーティリティ
│   └── types/                   # 型定義
├── prisma/
│   └── schema.prisma            # データベースモデル
├── docs/                        # ドキュメント
├── docker/                      # Docker 設定
└── scripts/                     # スクリプト
```

---

## 🎨 デザインの特徴

### 中国赤テーマ

- メインカラー: `hsl(0, 84%, 50%)` (中国赤)
- ダークモードサポート
- モダン UI デザイン
- レスポンシブレイアウト

### UI コンポーネント

- Button (ボタン)
- Card (カード)
- Input (入力フィールド)
- Progress (プログレスバー)
- その他のコンポーネント...

---

## 🔧 開発コマンド

```bash
# 開発
npm run dev              # 開発サーバーを起動

# ビルド
npm run build            # 本番バージョンをビルド
npm start                # 本番サーバーを起動

# データベース
npm run db:generate      # Prisma Client を生成
npm run db:push          # Schema をプッシュ
npm run db:migrate       # マイグレーションを実行
npm run db:studio        # データベース管理画面を開く

# コード品質
npm run lint             # リント
```

---

## 🐳 Docker デプロイ

```bash
# docker ディレクトリに入る
cd docker

# サービスを起動
docker-compose up -d

# データベースを初期化
docker-compose exec app npx prisma db push

# ログを表示
docker-compose logs -f app

# サービスを停止
docker-compose down
```

---

## 📖 ドキュメント

- 📝 [クイックスタートガイド](./docs/快速起動説明.md) - 詳細な起動ガイド
- 📋 [要件仕様書](./docs/需求仕様文档.md) - 製品要件と機能
- 🏗️ [技術実装方案](./docs/技術実装方案ドキュメント.md) - 技術アーキテクチャと設計
- 🌐 [バックエンドAPIドキュメント](./docs/後端API接口ドキュメント.md) - API インターフェース仕様

---

## 🌍 サポートしている言語

英語、簡体字中国語、繁体字中国語、日本語、韓国語、スペイン語、フランス語、ドイツ語、ポルトガル語、ロシア語など20以上の言語

---

## 🤖 サポートしている AI モデル

- Claude 3.5 Sonnet (推奨)
- GPT-4o (推奨)
- Gemini Pro 1.5

---

## ⚠️ 注意事項

### Windows ユーザー

- **Git Bash** でスクリプトを実行
- MySQL サービスが起動していることを確認

### データベース

- MySQL 8.0+ が必要
- データベースが作成されていることを確認: `github_global`

### GitHub App

- ログインには設定必須
- Callback URL: `http://localhost:3000/api/auth/callback/github`
- 必要な権限:
  - Repository > Contents: Read & Write
  - Repository > Metadata: Read
  - Repository > Pull requests: Read & Write
  - Account > Email addresses: Read

---

## 🐛 よくある質問

### Q: 依存関係のインストールに失敗する?

```bash
# キャッシュをクリア
rm -rf node_modules package-lock.json
npm install
```

### Q: データベース接続に失敗する?

確認項目:
1. MySQL が起動しているか
2. `DATABASE_URL` の設定は正しいか
3. データベースは作成されているか

### Q: ページのスタイルが崩れる?

```bash
# 再ビルド
rm -rf .next
npm run dev
```

---

## 📧 ヘルプの取得

- ドキュメントを参照: `docs/` ディレクトリ
- ログを確認: 開発サーバーコンソール
- GitHub Issues: 問題を報告

---

## 🎉 使い始める

```bash
# ワンクリック起動 (スクリプトを使用)
bash scripts/setup.sh

# または手動で起動
npm install
npm run db:generate
npm run db:push
npm run dev
```

**お楽しみください! 🚀**