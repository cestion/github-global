The user wants me to translate a Markdown document from zh-CN (Simplified Chinese) to ja (Japanese). I need to:

1. Preserve all Markdown formatting (headers, lists, code blocks, links, etc.)
2. NOT translate code snippets, variable names, function names, or technical identifiers
3. NOT translate URLs, file paths, or command-line examples
4. Preserve the original document structure exactly
5. Maintain a professional and accurate translation tone
6. Keep inline code (`code`) untranslated
7. Translate comments in code blocks if they are in the source language
8. Preserve all HTML tags and their attributes
9. Keep emojis and special characters as-is
10. Do NOT add any explanations or notes - output ONLY the translated content

Let me translate this document carefully, keeping all the formatting and structure intact while translating only the Chinese text to Japanese.

I'll go through the document and translate each section:
</think>

# GitHub リポジトリ AI ドキュメント翻訳プラットフォーム

> 作者：[程序员鱼皮](https://yuyuanweb.feishu.cn/wiki/Abldw5WkjidySxkKxU2cQdAtnah)
>
> 本プロジェクトは教学プロジェクトで、完全な動画チュートリアル + 文字チュートリアル + 履歴書の書き方 + 面接問題の解答 + 質疑応答サービスを提供し、プロジェクトの能力を向上させ、履歴書にアクセントを加えます！
>
> ⭐️ プロジェクトシリーズへの参加：[プログラミングナビに参加](https://www.codefather.cn/vip)



## 一、プロジェクト紹介

これは **AI プログラミング実践** をコアとしたプロジェクトチュートリアルで、Next.js + GitHub App + OpenRouter をベースにし、AI プログラミング 방식으로 0 から 1 まで「GitHub リポジトリ AI ドキュメント翻訳 SaaS プラットフォーム」を開発します。AI Vibe Coding の完全なワークフローを体験し、AI で実際に使えて、デプロイできて収益化できる製品を 만드는 方法をお伝えします！

📺 プロジェクト紹介動画、快速確認成品効果：https://bilibili.com/video/BV1mAAmzqEfP

![](https://pic.yupi.icu/1/1769079083162-aa879560-6044-4ef7-a3a2-718b03070978-20260225143424199.png)

任意の GitHub リポジトリアドレスを入力すると、AI が自動的にドキュメントを多言語に翻訳し、ベース言語の内容が変更されたときに、**自動増分同期翻訳** を行い、PR を生成してリポジトリ担当者のマージを待ちます。全程人工介入不要です。

### なぜこのプロジェクトを作るのか？

魚皮は AI プログラミングチュートリアルリポジトリ [ai-guide](https://github.com/liyupi/ai-guide) をオープンソース化し、何百もの中国語チュートリアルドキュメントを含んでいます。海外ユーザーにも見てもらいたいと思い、リポジトリを多言語バージョンに翻訳したいですが、人工翻訳コストが高すぎ、GitHub Actions は自分で設定をいじる必要があり……

既然如此、**不如做一个更通用的ツール**。

これが GitHub Global プロジェクトの始まりです：任意の GitHub リポジトリアドレスを入力すると、AI が自動的にドキュメントを多言語に翻訳し、ベース言語の内容が変更されたときに、**自動増分同期翻訳** を行い、PR を生成してリポジトリ担当者のマージを待ちます。全程人工介入不要です。

ゼロ設定、ワンボタン翻訳で、GitHub プロジェクトを世界に広げましょう！

![](https://pic.yupi.icu/1/GitHub%2520Global%2520%25E4%25B8%25BB%25E9%25A1%25B5.png)



### 6 つのコア機能

1）GitHub アカウントでワンボタンログインし、GitHub App に基づいて安全なログインと認証を実現。

![](https://pic.yupi.icu/1/image-20260225142930323.png)



2）GitHub リポジトリをインポートし、アドレスを入力するだけで自動的にリポジトリ情報を取得。

![](https://pic.yupi.icu/1/1769079897565-92698844-bfcc-4f6d-b226-d18352ea2244-20260225144921746-20260225144924730.png)



3）翻訳設定、翻訳範囲とターゲット言語を選択可能（20 種類の主流言語をサポート）。

![](https://pic.yupi.icu/1/1769079897565-92698844-bfcc-4f6d-b226-d18352ea2244-20260225144921746-20260225144924730.png)



4）ワンボタンで翻訳を実行、リアルタイムで進捗を表示し、翻訳完了後に自動的に PR を作成。

![](https://pic.yupi.icu/1/1769079926879-90640105-2d23-418c-b4b5-e962eab31299-20260225144931498.png)

![](https://pic.yupi.icu/1/1769080074375-806fa172-c440-47e3-93fd-07ad33c271ea-20260225144935674.png)

リポジトリ担当者は自分で本次翻訳をマージするかどうかを選択でき、利便性と安全性を兼ね備えています：

![](https://pic.yupi.icu/1/1769080059408-f3e3d44f-df55-4872-8bdc-c781b71cfc81.png)



5）自動増分翻訳をトリガー、有効にすると每次 Push で自動的に変更されたドキュメントを翻訳。

![](https://pic.yupi.icu/1/1770201178863-f4e450bd-b92f-4f56-9b43-82aed36a73b0-20260225142203617.png)

![](https://pic.yupi.icu/1/1770201323050-d991c61a-2ffa-40c1-b1c8-4334ff05c248-20260225141729741.png)



6）カスタム大規模モデルと API Key、GPT、Claude、Gemini、DeepSeek などの主流モデルをサポート。

![](https://pic.yupi.icu/1/1770194573295-9e7552ca-b0c1-4612-a590-6060b5717d79-20260225144945946.png)



## 二、プロジェクト優位性

本プロジェクトのテーマは新颖で、AI プログラミング時代に準拠し、 **実際の SaaS 製品開発** を指向とし、CRUD のありふれたプロジェクトとは異なります。プロジェクト内容は洗練されており、 **一週間以内に学習完了** 可能で、AI プログラミングの完全なワークフローを習得でき、履歴書と就職活動において大幅に競争力を向上させます！

技術が豊富で、AI プログラミングの全チェーンをカバー：

![](https://pic.yupi.icu/1/image-20260225140224582.png)

このプロジェクトから学ぶことができます：

- AI でニーズ調査を行い、専門的な《ニーズ仕様書》を生成する方法？
- マルチ AI 並行方式で、同時にフロントエンドとバックエンドを開発する方法？
- GitHub App と連携し、安全な OAuth 認証とリポジトリ操作を実現する方法？
- OpenRouter に接続し、数百種類の AI 大規模モデルを統一して对接する方法？
- GitHub API を使用してリポジトリファイルツリー、ファイル提交、PR 作成を行う方法？
- GitHub Webhook を通じてイベント駆動の自動化翻訳を実現する方法？
- 内网穿透ツールを使用し、ローカルで Webhook コールバックをデバッグする方法？
- Vercel で Next.js フルスタックプロジェクトをデプロイし、快速上线する方法？
- AI 開発フローでのコードレビュー、バージョン管理と問題修正の方法？
- 競合製品の差別化機会を特定し、本当に競争力のある製品を設計する方法？




### 魚皮シリーズプロジェクトの優位性

魚皮のオリジナルプロジェクトは **実践** を主とし、 **全程ライブ配信** 方式で **0 から 1** まで帶做し、ニーズ分析、技術選定、プロジェクト設計、プロジェクト初期化、Demo 記述、前後端開発実装、プロジェクト最適化、デプロイ上线などの各环节において、私は **理論から実践** まで明確に説明し、すべての细节を見逃しません！

网上的教程と比較して学ぶ相比、鱼皮プロジェクトシリーズの優位性：知識を学ぶ => 実践プロジェクト => 復習ノート => プロジェクト質疑応答 => 履歴書の書き方 => 面接問題の解答までのワンストップサービス

![](https://pic.yupi.icu/1/image-20260225142355401.png)

プログラミングナビには既に **20+ 套プロジェクトチュートリアル！** 各プロジェクトの学習重点異なり、ほぼすべてがフロントエンド + バックエンドの **フルスタックプロジェクト** で、大量の AI アプリケーション開発プロジェクトもあります。

詳細については：[https://codefather.cn/course](https://www.codefather.cn/course)（当ページの右側にチュートリアル推奨と学習アドバイスがあります）

過去のプロジェクト紹介動画：[https://bilibili.com/video/BV1YvmbYbEgS](https://www.bilibili.com/video/BV1YvmbYbEgS/)

魚皮のプロジェクトは多くの学生が高給 Offer を獲得するのを助けました：

![](https://pic.yupi.icu/1/%E7%BC%96%E7%A8%8B%E5%AF%BC%E8%88%AA2026%20offer%E6%8A%A5%E5%96%9C.png)



## 三、より詳細な紹介

機能モジュール：

![](https://pic.yupi.icu/1/image-20260225140201706.png)

アーキテクチャ設計：

![](https://pic.yupi.icu/1/image-20260225141302579.png)



## 四、快速実行

> 詳細な保姆級チュートリアルは [ローカル実行ガイド](./docs/ローカル実行ガイド.md) をご覧ください

### 前提条件

- Node.js >= 20
- MySQL >= 8.0
- 一つの [GitHub App](https://github.com/settings/apps/new)（ログインとリポジトリ操作用）
- 一つの [OpenRouter API Key](https://openrouter.ai/keys)（AI 翻訳用）

### 1. クローンして依存関係をインストール

```bash
git clone https://github.com/liyupi/github-global.git
cd github-global
npm install
```

### 2. 環境変数の設定

```bash
# 環境変数ファイルを作成（2つのファイルの内容は同一に保つ）
cp .env.example .env
cp .env.example .env.local
```

`.env` と `.env.local` を編集し、構成を入力：

```bash
DATABASE_URL=mysql://root:あなたのパスワード@localhost:3306/github_global
NEXTAUTH_URL=http://localhost:3123
AUTH_SECRET=ランダム文字列32文字以上
GITHUB_APP_ID=あなたのAppID
GITHUB_APP_CLIENT_ID=あなたのClientID
GITHUB_APP_CLIENT_SECRET=あなたのClientSecret
GITHUB_APP_PRIVATE_KEY_PATH=./private-key.pem
PLATFORM_OPENROUTER_API_KEY=sk-or-v1-あなたのkey
```

GitHub App の秘密鍵ファイルをプロジェクトルートディレクトリの `private-key.pem` として保存します。

### 3. データベースの初期化と起動

```bash
# データベースを作成（MySQL コマンドライン）
mysql -u root -p -e "CREATE DATABASE github_global CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;"

# Prisma クライアントを生成 + テーブル作成
npx prisma generate
npx prisma db push

# 開発サーバーを起動
npm run dev
```

**http://localhost:3123** にアクセスして使用できます。

### Docker デプロイ

```bash
docker-compose up -d
docker-compose exec app npx prisma db push
```

詳細については [ローカル実行ガイド](./docs/ローカル実行ガイド.md) と [手動設定ドキュメント](./docs/手動設定ドキュメント.md) をご覧ください。

## プロジェクト学習への参加

プログラミングナビには既に **20+ 套プロジェクトチュートリアル**！各プロジェクトの学習重点異なり、ほぼすべてがフロントエンド + バックエンドの **フルスタック** プロジェクトで、大量の AI アプリケーション開発プロジェクトもあります。

![](https://pic.yupi.icu/1/%25E9%25A1%25B9%25E7%259B%25AE%25E6%2595%2599%25E7%25A8%258B.png)

[プログラミングナビ](https://www.codefather.cn/vip) への参加を歓迎します。参加後は全程本プロジェクトを追跡学習できるだけでなく、過去の **20+ 套オリジナルプロジェクトチュートリアル** もすべて無制限で視聴できます。さらに多くのオリジナル技術資料、学習と就職指導、百场以上の面接録画動画もあり、プログラミングテイクオフの旅を始めましょう！

🧧 新規プロジェクト学習支援のため、 **限定プログラミングナビクーポン** を配布します。QRコードでクーポンを领取して参加できます。参加後3日以内に不满意であれば全额返金可能，欢迎加入体験、名额有限、早速学習！

<img width="404" alt="image" src="https://github.com/user-attachments/assets/56411098-b60e-4267-8ba2-4ebc5d416afc" />

1 日あたり 1 元未満で、自分への最も価値のある投資です！プログラミングナビ会員になると、20 以上のプロジェクトのチュートリアルと資料を解除でき、PC ウェブサイトと APP で学習できます。如図：

![](https://pic.yupi.icu/1/image-20250120113756426-20250422160856746.png)