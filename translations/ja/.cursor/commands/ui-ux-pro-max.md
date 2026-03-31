The user wants me to translate a Markdown document from zh-CN to ja. Let me analyze the content:

1. This is a technical documentation file about a UI/UX design guide tool called "ui-ux-pro-max"
2. It contains instructions for using a Python script to search for design recommendations
3. There are code blocks, tables, and various formatting elements

Key rules to follow:
- Preserve all Markdown formatting
- Do NOT translate code snippets, variable names, function names
- Do NOT translate URLs, file paths, or command-line examples
- Translate comments in code blocks if they are in the source language (but these appear to be in English already)
- Preserve HTML tags and their attributes
- Keep emojis and special characters as-is
- Output ONLY the translated content

Looking at the content, it's actually already in English! The user said "from zh-CN to ja" but the content is already in English. Let me check again...

Wait, I see the issue. The user said "Translate the following Markdown content from zh-CN to ja" but the content provided is already in English. This seems like a mismatch. However, I should follow the instruction as given - perhaps the user made a mistake or perhaps they want me to translate from English to Japanese.

Actually, looking more carefully at the content, it appears to be in English already. The user's request says "from zh-CN to ja" but the source is English. This is confusing.

Let me re-read the instructions:
- "Your task is to translate Markdown documents from zh-CN to ja"

But the provided content is in English. I think the user may have made an error in their request, or perhaps they want me to translate from English to Japanese anyway.

Given the explicit instruction to translate "from zh-CN to ja", and the content is in English, I have a few options:
1. Ask for clarification
2. Assume it's a mistake and the content should be treated as if it were in zh-CN


3. Translate from English to Japanese as the user seems to want

I'll proceed with translating from English to Japanese, following the rules for technical documentation translation. I'll focus on maintaining the technical accuracy while adapting the language to Japanese conventions.

The key challenge is ensuring the translation preserves the precise technical meaning while sounding natural in Japanese. I'll carefully translate each section, paying special attention to technical terms and command-line instructions.

I'll keep code blocks, URLs, and technical identifiers in their original form, as per the translation guidelines. The goal is to create a Japanese version that technical users can easily understand and follow.
</think>

# ui-ux-pro-max

Webおよびモバイルアプリケーションのための総合デザインガイド。50以上のスタイル、97のカラーパレット、57のフォントペアリング、99のUXガイドライン、9つの技術スタックにわたる25のチャートタイプを収録。優先順位に基づく推奨事項を備えた検索可能なデータベース。

## 前提条件

Pythonがインストールされているか確認します：

```bash
python3 --version || python --version
```

Pythonがインストールされていない場合は、ユーザーのOSに基づいてインストールしてください：

**macOS:**
```bash
brew install python3
```

**Ubuntu/Debian:**
```bash
sudo apt update && sudo apt install python3
```

**Windows:**
```powershell
winget install Python.Python.3.12
```

---

## このワークフローの使用方法

ユーザーがUI/UX作業（デザイン、構築、作成、実装、レビュー、修正、改善）を要求した場合、このワークフローに従ってください：

### ステップ1：ユーザー要件の分析

ユーザーからの要求から主要な情報を抽出します：
- **製品タイプ**: SaaS、eコマース、ポートフォリオ、ダッシュボード、ランディングページなど
- **スタイルキーワード**: ミニマル、プレイフル、プロフェッショナル、エレガント、ダークモードなど
- **業界**: ヘルスケア、FinTech、ゲーム、教育など
- **スタック**: React、Vue、Next.js、またはデフォルトで`html-tailwind`

### ステップ2：デザインシステムの生成（必須）

包括的な推奨事項と理由を得るために、**常に`--design-system`**から始めてください：

```bash
python3 .shared/ui-ux-pro-max/scripts/search.py "<product_type> <industry> <keywords>" --design-system [-p "Project Name"]
```

このコマンドは：
1. 5つのドメインを並行して検索（product、style、color、landing、typography）
2. `ui-reasoning.csv`からの推論ルールを適用して最良の一致を選択
3. 完全なデザインシステムを返す：パターン、スタイル、カラー、タイポグラフィ、エフェクト
4. 避けるべきアンチパターンを含む

**例：**
```bash
python3 .shared/ui-ux-pro-max/scripts/search.py "beauty spa wellness service" --design-system -p "Serenity Spa"
```

### ステップ2b：デザインシステムの永続化（マスター + オーバーライドパターン）

セッション間で階層的に取得するためにデザインシステムを保存するには、`--persist`を追加します：

```bash
python3 .shared/ui-ux-pro-max/scripts/search.py "<query>" --design-system --persist -p "Project Name"
```

これにより作成されます：
- `design-system/MASTER.md` — すべてのデザインルールを持つグローバルな真実の源
- `design-system/pages/` — ページ固有のオーバーライド用フォルダ

**ページ固有のオーバーライド付き：**
```bash
python3 .shared/ui-ux-pro-max/scripts/search.py "<query>" --design-system --persist -p "Project Name" --page "dashboard"
```

これによりこれも作成されます：
- `design-system/pages/dashboard.md` — マスターからのページ固有の逸脱

**階層的取得の仕組み：**
1. 特定のページ（例：「Checkout」）を構築する場合、まず`design-system/pages/checkout.md`を確認
2. ページファイルが存在する場合、そのルールはマスターファイルを**オーバーライド**します
3. 存在しない場合は、`design-system/MASTER.md`のみを使用

### ステップ3：詳細な検索で補完（必要に応じて）

デザインシステムを取得した後、ドメイン検索を使用して詳細を取得します：

```bash
python3 .shared/ui-ux-pro-max/scripts/search.py "<keyword>" --domain <domain> [-n <max_results>]
```

**詳細な検索を使用するタイミング：**

| 必要性 | ドメイン | 例 |
|------|--------|---------|
| その他のスタイルオプション | `style` | `--domain style "glassmorphism dark"` |
| チャート推奨 | `chart` | `--domain chart "real-time dashboard"` |
| UXベストプラクティス | `ux` | `--domain ux "animation accessibility"` |
| 代替フォント | `typography` | `--domain typography "elegant luxury"` |
| ランディング構造 | `landing` | `--domain landing "hero social-proof"` |

### ステップ4：スタックガイドライン（デフォルト：html-tailwind）

実装固有のベストプラクティスを取得します。ユーザーがスタックを指定しない場合、**デフォルトで`html-tailwind`**を使用します。

```bash
python3 .shared/ui-ux-pro-max/scripts/search.py "<keyword>" --stack html-tailwind
```

利用可能なスタック：`html-tailwind`、`react`、`nextjs`、`vue`、`svelte`、`swiftui`、`react-native`、`flutter`、`shadcn`、`jetpack-compose`
, `jetpack-compose`
---

## 検索リファレンス

### 利用可能なドメイン

| ドメイン | 用途 | 例キーワード |
|--------|---------|------------------|
| `product` | 製品タイプの推奨事項 | SaaS、eコマース、ポートフォリオ、ヘルスケア、beauty、service |
| `style` | UIスタイル、カラー、エフェクト | glassmorphism、minimalism、dark mode、brutalism |
| `typography` | フォントペアリング、Google Fonts | elegant、playful、professional、modern |
| `color` | 製品タイプ別カラーパレット | saas、ecommerce、healthcare、beauty、fintech、service |
| `landing` | ページ構造、CTA戦略 | hero、hero-centric、testimonial、pricing、social-proof |
| `chart` | チャートタイプ、ライブラリ推奨 | trend、comparison、timeline、funnel、pie |
| `ux` | ベストプラクティス、アンチパターン | animation、accessibility、z-index、loading |
| `react` | React/Next.jsパフォーマンス | waterfall、bundle、suspense、memo、rerender、cache |
| `web` | Webインターフェースガイドライン | aria、focus、keyboard、semantic、virtualize |
| `prompt` | AIプロンプト、CSSキーワード | （スタイル名） |

### 利用可能なスタック

| スタック | フォーカス |
|-------|-------|
| `html-tailwind` | Tailwindユーティリティ、レスポンシブ、a11y（デフォルト） |
| `react` | 状態、フック、パフォーマンス、パターン |
| `nextjs` | SSR、ルーティング、画像、APIルート |
| `vue` | Composition API、Pinia、Vue Router |
| `svelte` | Runes、stores、SvelteKit |
| `swiftui` | Views、State、Navigation、Animation |
| `react-native` | Components、Navigation、Lists |
| `flutter` | Widgets、State、Layout、Theming |
| `shadcn` | shadcn/uiコンポーネント、テーマ設定、フォーム、パターン |
| `jetpack-compose` | Composables、Modifiers、State Hoisting、Recomposition |

---

## ワークフローの例

**ユーザーの要求：** "Làm landing page cho dịch vụ chăm sóc da chuyên nghiệp"

### ステップ1：要件の分析
- 製品タイプ：Beauty/Spaサービス
- スタイルキーワード：elegant、professional、soft
- 業界：Beauty/Wellness
- スタック：html-tailwind（デフォルト）

### ステップ2：デザインシステムの生成（必須）

```bash
python3 .shared/ui-ux-pro-max/scripts/search.py "beauty spa wellness service elegant" --design-system -p "Serenity Spa"
```

**出力：** パターン、スタイル、カラー、タイポグラフィ、エフェクト、アンチパターンを含む完全なデザインシステム。

### ステップ3：詳細な検索で補完（必要に応じて）

```bash
# アニメーションとアクセシビリティのUXガイドラインを取得
python3 .shared/ui-ux-pro-max/scripts/search.py "animation accessibility" --domain ux

# 必要に応じて代替タイポグラフィオプションを取得
python3 .shared/ui-ux-pro-max/scripts/search.py "elegant luxury serif" --domain typography
```

### ステップ4：スタックガイドライン

```bash
python3 .shared/ui-ux-pro-max/scripts/search.py "layout responsive form" --stack html-tailwind
```

**その後：** デザインシステム + 詳細な検索を統合して、デザインを実装します。

---

## 出力形式

`--design-system`フラグは2つの出力形式をサポートしています：

```bash
# ASCIIボックス（デフォルト）- ターミナル表示に最適
python3 .shared/ui-ux-pro-max/scripts/search.py "fintech crypto" --design-system

# Markdown - ドキュメントに最適
python3 .shared/ui-ux-pro-max/scripts/search.py "fintech crypto" --design-system -f markdown
```

---

## より良い結果のためのヒント

1. **キーワードを具体的にする** - "healthcare SaaS dashboard" > "app"
2. **複数回検索する** - 異なるキーワードは異なる洞察をもたらす
3. **ドメインを組み合わせる** - Style + Typography + Color = 完全なデザインシステム
4. **常にUXを確認する** - 一般的な問題について"animation"、"z-index"、"accessibility"を検索
5. **スタックフラグを使用する** - 実装固有のベストプラクティスを取得
6. **反復する** - 最初の検索が一致しない場合、異なるキーワードを試す

---

## プロフェッショナルなUIのための一般的なルール

UIを非プロフェッショナルに見せる見落とされがちな問題：

### アイコンと視覚要素

| ルール | する | しない |
|------|----|----- |
| **絵文字アイコンなし** | SVGアイコンを使用（Heroicons、Lucide、Simple Icons） | 🎨 🚀 ⚙️などの絵文字をUIアイコンとして使用 |
| **安定したホバー状態** | ホバー時にカラー/不透明度の遷移を使用 | レイアウトをシフトするスケール変換を使用 |
| **正しいブランドロゴ** | Simple Iconsからの公式SVGを調査 | 推測したり正しくないロゴパスを使用 |
| **一貫したアイコンサイズ** | w-6 h-6で固定viewBox（24x24）を使用 | 異なるアイコンサイズをランダムに混在させない |

### インタラクションとカーソル

| ルール | する | しない |
|------|----|----- |
| **カーソルポインター** | すべてのクリック可能/ホバー可能なカードに`cursor-pointer`を追加 | インタラクティブな要素でデフォルトカーソルをそのまま |
| **ホバーフィードバック** | 視覚的フィードバックを提供（カラー、シャドウ、ボーダー） | 要素がインタラクティブであることを示すがない |
| **スムーズな遷移** | `transition-colors duration-200`を使用 | インスタントな状態変更または遅すぎる（500ms以上） |

### ライト/ダークモードのコントラスト

| ルール | する | しない |
|------|----|----- |
| **ガラスカードライトモード** | `bg-white/80`以上の不透明度を使用 | `bg-white/10`を使用（透明すぎる） |
| **テキストコントラストライト** | テキストに`#0F172A`（slate-900）を使用 | 本文テキストに`#94A3B8`（slate-400）を使用 |
| **ミュートテキストライト** | 最低`#475569`（slate-600）を使用 | gray-400以下を使用 |
| **ボーダーの可視性** | ライトモードで`border-gray-200`を使用 | `border-white/10`を使用（見えない） |

### レイアウトとスペーシング

| ルール | する | しない |
|------|----|----- |
| **フローティングナビゲーションバー** | `top-4 left-4 right-4`のスペーシングを追加 | ナビゲーションバーを`top-0 left-0 right-0`に貼り付け |
| **コンテンツパディング** | 固定ナビゲーションバーの高さを考慮 | 固定要素の背後にコンテンツを隠す |
| **一貫した最大幅** | 同じ`max-w-6xl`または`max-w-7xl`を使用 | 異なるコンテナ幅を混在させる |

---

## 納入前チェックリスト

UIコードを納入する前に、以下の項目を確認してください：

### 視覚品質
- [ ] 絵文字をアイコンとして使用していない（代わりにSVGを使用）
- [ ] すべてのアイコンが一貫したアイコンセットから（Heroicons/Lucide）
- [ ] ブランドロゴが正しい（Simple Iconsから確認）
- [ ] ホバー状態がレイアウトシフトを引き起こさない
- [ ] var()ラッパーではなくテーマカラーを直接使用（bg-primary）

### インタラクション
- [ ] すべてのクリック可能な要素に`cursor-pointer`がある
- [ ] ホバー状態が明確な視覚的フィードバックを提供
- [ ] 遷移がスムーズ（150-300ms）
- [ ] キーボードナビゲーション用のフォーカス状態が可視

### ライト/ダークモード
- [ ] ライトモードのテキストに十分なコントラスト（最低4.5:1）
- [ ] ライトモードでガラス/透明要素が可視
- [ ] 両方のモードでボーダーが可視
- [ ] 納入前に両方のモードをテスト

### レイアウト
- [ ] フローティング要素が端から適切なスペーシングがある
- [ ] 固定ナビゲーションバーの背後に隠れたコンテンツがない
- [ ] 375px、768px、1024px、1440pxでレスポンシブ
- [ ] モバイルで水平スクロールがない

### アクセシビリティ
- [ ] すべての画像にaltテキストがある
- [ ] フォーム入力にラベルがある
- [ ] 色が唯一の指標ではない
- [ ] `prefers-reduced-motion`が尊重されている