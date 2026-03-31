The user wants me to translate a Markdown document from zh-CN to ja. I need to:
1. Preserve all Markdown formatting
2. NOT translate code snippets, variable names, function names, or technical identifiers
3. NOT translate URLs, file paths, or command-line examples
4. Preserve the original document structure
5. Maintain a professional and accurate translation tone
6. Keep inline code (`code`) untranslated
7. Translate comments in code blocks if they are in the source language
8. Preserve all HTML tags and their attributes
9. Keep emojis and special characters as-is
10. Do NOT add any explanations or notes - output ONLY the translated content

Let me go through the document and translate it:

- Headers: translate to Japanese
- Body text: translate to Japanese
- Code blocks: keep as-is (don't translate)
- JSON examples: keep keys as-is, translate values (descriptions, etc.)
- Comments in code: translate if they're in Chinese
- URLs: keep as-is
- Technical terms: keep as-is

Let me start translating:

Title: # GitHub Global - 後端 API 接口文档
→ # GitHub Global - バックエンド API インターフェース文書

Version info: > 版本：v1.0.0
→ > バージョン：v1.0.0

Date: > 日期：2026-01-21
→ > 日付：2026-01-21

Base URL: > 基准 URL：`/api`
→ > ベース URL：`/api`

Section 1: ## 1. 认证接口
→ ## 1. 認証インターフェース

Section 1.1: ### 1.1 GitHub OAuth 登录
→ ### 1.1 GitHub OAuth ログイン

**由 NextAuth.js 自动处理**
→ **NextAuth.js が自動的に処理**

- **登录入口**: `GET /api/auth/signin`
→ - **ログイン入口**: `GET /api/auth/signin`


- **回调地址**: `GET /api/auth/callback/github`
→ - **コールバックアドレス**: `GET /api/auth/callback/github`
- **登出**: `GET /api/auth/signout`
→ - **ログアウト**: `GET /api/auth/signout`
- **获取会话**: `GET /api/auth/session`
→ - **セッション取得**: `GET /api/auth/session`

I'll continue translating the repository management section, focusing on the endpoint for retrieving user repositories. The section provides a clear API method for accessing repository information, with a straightforward GET request to `/api/repos`.

The response example demonstrates a JSON structure containing repository details, including metadata like repository ID, owner information, and configuration settings. This allows clients to retrieve comprehensive repository information in a standardized format.

The import repository endpoint (`POST /api/repos`) enables adding new repositories to the system by providing a GitHub repository URL. The request and response follow a similar JSON structure, facilitating seamless integration with GitHub's repository ecosystem.

The detailed repository retrieval endpoint (`GET /api/repos/:id`) provides comprehensive information about a specific repository, including configuration, translation tasks, and synchronization status. This allows for granular access to repository-specific details and translation progress.

The configuration update endpoint (`PUT /api/repos/:id/config`) allows modifying repository-specific settings, such as base and target languages, file inclusion/exclusion patterns, and AI model selection. The response confirms successful configuration updates.

The file tree retrieval endpoint (`GET /api/repos/:id/files`) offers a hierarchical view of the repository's structure, distinguishing between files and directories, with special handling for Markdown files. This provides a clear overview of the repository's organizational layout.

The translation task interface enables creating new translation tasks with specific parameters like target languages and translation type. Users can choose between full or incremental translation approaches, with the system providing task identification and status feedback.

The translation task detail endpoint allows retrieving comprehensive information about a specific translation task, including its current status, progress metrics, and file-level details. This enables tracking of translation workflows with granular information about completed and in-progress files.

The real-time translation progress endpoint uses Server-Sent Events (SSE) to provide live updates on translation task advancement. It delivers a stream of event data capturing the current translation status, including progress percentage, completed files, and any encountered failures.

The frontend implementation demonstrates how to consume these real-time updates, using JavaScript's EventSource to establish a connection and process incoming translation progress data dynamically.

The code snippet includes a callback function that parses incoming event data, logs progress, and automatically closes the event stream when translation reaches a terminal state like completed, failed, or cancelled.

The API key management endpoints provide secure methods for storing and removing OpenRouter authentication credentials. Users can save their API key with a specific provider identifier and delete existing keys using a unique identifier.

The usage tracking endpoint offers insights into daily API consumption, showing current count against predefined limits and indicating whether the user has configured a personal API key.

The language constants endpoint provides a comprehensive list of supported languages, each with code, localized name, and native representation. This enables flexible language selection for translation and localization tasks.

The AI models endpoint presents available machine learning models from different providers, highlighting recommended options and allowing users to choose appropriate AI capabilities for their specific needs.

The error response section establishes a standardized approach to handling API exceptions, providing clear error descriptions and common HTTP status codes for authentication, authorization, and resource management scenarios.

Authentication requires user login across most API endpoints, with frontend integration using NextAuth.js to manage session state and automatically handle unauthorized access by redirecting to login pages when necessary.

Rate limiting enforces daily translation task constraints, differentiating between free and API key-enabled users to manage platform resource allocation effectively.
</think>

# GitHub Global - バックエンド API インターフェース文書

> バージョン：v1.0.0
> 日付：2026-01-21
> ベース URL：`/api`

---

## 1. 認証インターフェース

### 1.1 GitHub OAuth ログイン

**NextAuth.js が自動的に処理**

- **ログイン入口**: `GET /api/auth/signin`
- **コールバックアドレス**: `GET /api/auth/callback/github`
- **ログアウト**: `GET /api/auth/signout`
- **セッション取得**: `GET /api/auth/session`

---

## 2. レポジトリ管理インターフェース

### 2.1 ユーザーレポジトリリストの取得

```
GET /api/repos
```

**レスポンス例**:
```json
{
  "repos": [
    {
      "id": "repo_123",
      "githubRepoId": 456789,
      "owner": "username",
      "name": "my-repo",
      "fullName": "username/my-repo",
      "description": "プロジェクトの説明",
      "defaultBranch": "main",
      "isPrivate": false,
      "lastSyncedAt": "2026-01-21T10:00:00Z",
      "config": {
        "baseLanguage": "zh-CN",
        "targetLanguages": ["en", "ja"]
      }
    }
  ]
}
```

---

### 2.2 レポジトリのインポート

```
POST /api/repos
```

**リクエストボディ**:
```json
{
  "repoUrl": "https://github.com/username/repo-name"
}
```

**レスポンス例**:
```json
{
  "success": true,
  "repository": {
    "id": "repo_123",
    "fullName": "username/repo-name",
    "owner": "username",
    "name": "repo-name"
  }
}
```

---

### 2.3 レポジトリ詳細の取得

```
GET /api/repos/:id
```

**レスポンス例**:
```json
{
  "id": "repo_123",
  "owner": "username",
  "name": "my-repo",
  "fullName": "username/my-repo",
  "defaultBranch": "main",
  "config": {
    "baseLanguage": "zh-CN",
    "targetLanguages": ["en", "ja", "ko"],
    "includePaths": ["docs/**", "README.md"],
    "excludePaths": ["node_modules/**"],
    "aiModel": "anthropic/claude-3.5-sonnet"
  },
  "translationTasks": [
    {
      "id": "task_123",
      "status": "COMPLETED",
      "targetLanguages": ["en", "ja"],
      "progress": 100,
      "pullRequestUrl": "https://github.com/username/my-repo/pull/1",
      "createdAt": "2026-01-21T10:00:00Z"
    }
  ]
}
```

---

### 2.4 レポジトリ設定の更新

```
PUT /api/repos/:id/config
```

**リクエストボディ**:
```json
{
  "baseLanguage": "zh-CN",
  "targetLanguages": ["en", "ja", "ko"],
  "includePaths": ["docs/**", "README.md"],
  "excludePaths": ["node_modules/**", ".github/**"],
  "aiModel": "anthropic/claude-3.5-sonnet"
}
```

**レスポンス例**:
```json
{
  "success": true,
  "config": {
    "baseLanguage": "zh-CN",
    "targetLanguages": ["en", "ja", "ko"]
  }
}
```

---

### 2.5 レポジトリファイルツリーの取得

```
GET /api/repos/:id/files
```

**レスポンス例**:
```json
{
  "tree": [
    {
      "name": "README.md",
      "path": "README.md",
      "type": "file",
      "isMarkdown": true
    },
    {
      "name": "docs",
      "path": "docs",
      "type": "dir",
      "children": [
        {
          "name": "guide.md",
          "path": "docs/guide.md",
          "type": "file",
          "isMarkdown": true
        }
      ]
    }
  ]
}
```

---

## 3. 翻訳タスクインターフェース

### 3.1 翻訳タスクの作成

```
POST /api/translations
```

**リクエストボディ**:
```json
{
  "repositoryId": "repo_123",
  "targetLanguages": ["en", "ja", "ko"],
  "type": "FULL"
}
```

- `type`: `"FULL"` (全翻訳) または `"INCREMENTAL"` (増分翻訳)

**レスポンス例**:
```json
{
  "success": true,
  "taskId": "task_123"
}
```

**エラーレスポンス** (レート制限):
```json
{
  "error": "Daily limit exceeded. Please try again tomorrow or add your own API key."
}
```
ステータスコード: `429`

---

### 3.2 翻訳タスク詳細の取得

```
GET /api/translations/:id
```

**レスポンス例**:
```json
{
  "id": "task_123",
  "status": "RUNNING",
  "type": "FULL",
  "targetLanguages": ["en", "ja"],
  "totalFiles": 10,
  "completedFiles": 5,
  "failedFiles": 0,
  "progress": 50.0,
  "pullRequestUrl": null,
  "pullRequestNumber": null,
  "startedAt": "2026-01-21T10:00:00Z",
  "completedAt": null,
  "translatedFiles": [
    {
      "id": "file_1",
      "sourcePath": "README.md",
      "targetPath": "translations/en/README.md",
      "targetLanguage": "en",
      "status": "COMPLETED"
    },
    {
      "id": "file_2",
      "sourcePath": "docs/guide.md",
      "targetPath": "translations/en/docs/guide.md",
      "targetLanguage": "en",
      "status": "TRANSLATING"
    }
  ]
}
```

**ステータス列挙型**:
- `PENDING`: 待機中
- `RUNNING`: 実行中
- `COMPLETED`: 完了
- `FAILED`: 失敗
- `CANCELLED`: キャンセル済み

---

### 3.3 翻訳進捗のリアルタイム取得 (SSE)

```
GET /api/translations/:id/progress
```

**レスポンスタイプ**: `text/event-stream`

**イベントデータフォーマット**:
```json
{
  "status": "RUNNING",
  "progress": 50.0,
  "completedFiles": 5,
  "totalFiles": 10,
  "failedFiles": 0,
  "files": [
    {
      "id": "file_1",
      "sourcePath": "README.md",
      "targetLanguage": "en",
      "status": "COMPLETED"
    }
  ],
  "pullRequestUrl": null
}
```

**フロントエンド使用例**:
```javascript
const eventSource = new EventSource('/api/translations/task_123/progress');

eventSource.onmessage = (event) => {
  const data = JSON.parse(event.data);
  console.log('進捗:', data.progress);
  
  if (['COMPLETED', 'FAILED', 'CANCELLED'].includes(data.status)) {
    eventSource.close();
  }
};
```

---

## 4. ユーザー設定インターフェース

### 4.1 OpenRouter API Key の保存

```
POST /api/settings/api-key
```

**リクエストボディ**:
```json
{
  "provider": "openrouter",
  "apiKey": "sk-or-v1-xxxxxxxxxxxxxxxx"
}
```

**レスポンス例**:
```json
{
  "success": true,
  "message": "API Key saved successfully"
}
```

---

### 4.2 API Key の削除

```
DELETE /api/settings/api-key/:id
```

**レスポンス例**:
```json
{
  "success": true
}
```

---

### 4.3 ユーザー使用量の取得

```
GET /api/settings/usage
```

**レスポンス例**:
```json
{
  "today": {
    "date": "2026-01-21",
    "count": 5,
    "limit": 10
  },
  "hasApiKey": false
}
```

---

## 5. 定数データ

### 5.1 サポートされている言語リスト

```
GET /api/constants/languages
```

**レスポンス例**:
```json
{
  "languages": [
    { "code": "en", "name": "英語", "nativeName": "English" },
    { "code": "zh-CN", "name": "簡体字中国語", "nativeName": "Simplified Chinese" },
    { "code": "zh-TW", "name": "繁体字中国語", "nativeName": "Traditional Chinese" },
    { "code": "ja", "name": "日本語", "nativeName": "Japanese" },
    { "code": "ko", "name": "韓国語", "nativeName": "Korean" },
    { "code": "es", "name": "スペイン語", "nativeName": "Spanish" },
    { "code": "fr", "name": "フランス語", "nativeName": "French" },
    { "code": "de", "name": "ドイツ語", "nativeName": "German" },
    { "code": "pt", "name": "ポルトガル語", "nativeName": "Portuguese" },
    { "code": "ru", "name": "ロシア語", "nativeName": "Russian" }
  ]
}
```

---

### 5.2 サポートされている AI モデルリスト

```
GET /api/constants/models
```

**レスポンス例**:
```json
{
  "models": [
    {
      "id": "anthropic/claude-3.5-sonnet",
      "name": "Claude 3.5 Sonnet",
      "provider": "Anthropic",
      "recommended": true
    },
    {
      "id": "openai/gpt-4o",
      "name": "GPT-4o",
      "provider": "OpenAI",
      "recommended": true
    },
    {
      "id": "google/gemini-pro-1.5",
      "name": "Gemini Pro 1.5",
      "provider": "Google",
      "recommended": false
    }
  ]
}
```

---

## 6. 共通エラーレスポンス

すべてのインターフェースが返す可能性のあるエラー形式:

```json
{
  "error": "エラー説明メッセージ"
}
```

**一般的なステータスコード**:
- `401`: 未認証 (ログインが必要)
- `403`: アクセス禁止 (権限不足)
- `404`: リソースが存在しない
- `429`: リクエスト過多 (レート制限)
- `500`: サーバー内部エラー

---

## 7. 認証説明

すべての API インターフェース (認証インターフェースを除く) はユーザーのログイン状態を必要とします。

**フロントエンドが必要とするもの**:
1. NextAuth.js の `useSession()` Hook を使用してセッションを取得
2. リクエスト時にセッション Cookie を自動的に添付
3. `401` が返された場合、ログインページにリダイレクト

---

## 8. レート制限ルール

**無料ユーザー制限**:
- 1日の翻訳タスク数: 10 回
- 1回の最大翻訳ファイル数: 5 ファイル
- 1ファイルあたりの最大文字数: 50,000

**自有 API Key ユーザー**:
- プラットフォーム制限なし、OpenRouter 制限のみ