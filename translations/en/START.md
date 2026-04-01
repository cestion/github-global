The user wants me to translate a Markdown document from zh-CN to en. I need to:

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

Let me go through the document and translate it:

The document is about GitHub Global - a project that helps with translation tasks for GitHub repositories. Let me translate it carefully.

Key things to translate:
- Headers
- Descriptions
- Comments in code blocks (like "# 数据库" -> "# Database")
- UI text
- Documentation links text

Things NOT to translate:
- Code blocks (bash commands, env variables, etc.)
- File paths
- URLs
- Technical terms like DATABASE_URL, NEXTAUTH_SECRET, etc.
- Package names like npm, prisma, etc.

Let me start translating:
</think>

# 🚀 GitHub Global - Get Started Now

## Quickest Way to Start (3 Steps)

### 1️⃣ Install Dependencies

```bash
npm install
```

### 2️⃣ Configure Environment Variables

Create `.env` file:

```bash
# Copy example file
cp .env.example .env
```

**Minimum Configuration** (Required):

```env
# Database
DATABASE_URL="mysql://root:password@localhost:3306/github_global"

# NextAuth
NEXTAUTH_URL="http://localhost:3000"
NEXTAUTH_SECRET="your-random-secret"

# Encryption Key
ENCRYPTION_KEY="your-32-byte-hex-key"

# GitHub App (Fill in after creation)
GITHUB_APP_ID="your-app-id"
GITHUB_APP_CLIENT_ID="your-client-id"
GITHUB_APP_CLIENT_SECRET="your-client-secret"
GITHUB_APP_PRIVATE_KEY="your-private-key"
```

**Generate Keys**:

```bash
# NEXTAUTH_SECRET
openssl rand -base64 32

# ENCRYPTION_KEY
node -e "console.log(require('crypto').randomBytes(32).toString('hex'))"
```

**Create GitHub App**: Visit https://github.com/settings/apps/new

### 3️⃣ Initialize and Start

```bash
# Generate Prisma Client
npm run db:generate

# Initialize Database
npm run db:push

# Start Development Server
npm run dev
```

Visit: **http://localhost:3000**

---

## 🎯 Features

✅ **Implemented Features**:

- ✨ Home Page and Product Introduction
- 🔐 GitHub OAuth Login (NextAuth.js)
- 📊 Dashboard - Repository List Management
- 🗂️ Repository Details - View Translation Tasks
- ⚙️ Translation Config - Language and File Scope Selection
- 🔧 Settings Page - API Key Management
- 🗄️ Database Design (Prisma + MySQL)
- 🎨 Chinese Red Theme UI (Tailwind CSS)
- 📱 Responsive Design

🚧 **Pending Features** (Require Backend Integration):

- GitHub API Integration
- OpenRouter AI Translation
- Translation Task Queue
- Real-time Progress Display (SSE)
- Auto PR Creation

---

## 📁 Project Structure

```
github-global/
├── src/
│   ├── app/                      # Next.js Pages
│   │   ├── page.tsx             # Home Page
│   │   ├── dashboard/           # Dashboard
│   │   ├── repo/[id]/           # Repository Details
│   │   │   ├── page.tsx         # Repository Home
│   │   │   └── config/          # Translation Config
│   │   ├── settings/            # Settings Page
│   │   └── api/                 # API Routes
│   ├── components/ui/           # UI Components
│   ├── lib/                     # Utilities
│   └── types/                   # Type Definitions
├── prisma/
│   └── schema.prisma            # Database Schema
├── docs/                        # Documentation
├── docker/                      # Docker Configuration
└── scripts/                     # Scripts
```

---

## 🎨 Design Highlights

### Chinese Red Theme

- Primary Color: `hsl(0, 84%, 50%)` (Chinese Red)
- Dark Mode Support
- Modern UI Design
- Responsive Layout

### UI Components

- Button
- Card
- Input
- Progress
- More Components...

---

## 🔧 Development Commands

```bash
# Development
npm run dev              # Start Development Server

# Build
npm run build            # Build Production Version
npm start                # Start Production Server

# Database
npm run db:generate      # Generate Prisma Client
npm run db:push          # Push Schema
npm run db:migrate       # Run Migrations
npm run db:studio        # Open Database Management UI

# Code Quality
npm run lint             # Lint Code
```

---

## 🐳 Docker Deployment

```bash
# Enter docker directory
cd docker

# Start Services
docker-compose up -d

# Initialize Database
docker-compose exec app npx prisma db push

# View Logs
docker-compose logs -f app

# Stop Services
docker-compose down
```

---

## 📖 Documentation

- 📝 [Quick Start Guide](./docs/QuickStart.md) - Detailed Startup Guide
- 📋 [Requirements Specification](./docs/Requirements.md) - Product Requirements and Features
- 🏗️ [Technical Implementation](./docs/TechnicalDesign.md) - Technical Architecture and Design
- 🌐 [Backend API Documentation](./docs/BackendAPI.md) - API Interface Specification

---

## 🌍 Supported Languages

English, Simplified Chinese, Traditional Chinese, Japanese, Korean, Spanish, French, German, Portuguese, Russian and 20+ more languages

---

## 🤖 Supported AI Models

- Claude 3.5 Sonnet (Recommended)
- GPT-4o (Recommended)
- Gemini Pro 1.5

---

## ⚠️ Notes

### Windows Users

- Use **Git Bash** to run scripts
- Ensure MySQL service is running

### Database

- MySQL 8.0+ Required
- Ensure database is created: `github_global`

### GitHub App

- Must be configured to log in
- Callback URL: `http://localhost:3000/api/auth/callback/github`
- Required Permissions:
  - Repository > Contents: Read & Write
  - Repository > Metadata: Read
  - Repository > Pull requests: Read & Write
  - Account > Email addresses: Read

---

## 🐛 FAQ

### Q: Dependency Installation Failed?

```bash
# Clean Cache
rm -rf node_modules package-lock.json
npm install
```

### Q: Database Connection Failed?

Check:
1. Is MySQL running
2. Is `DATABASE_URL` configured correctly
3. Is the database created

### Q: Page Styles Incorrect?

```bash
# Rebuild
rm -rf .next
npm run dev
```

---

## 📧 Get Help

- Check Documentation: `docs/` directory
- Check Logs: Development Server Console
- GitHub Issues: Submit Issues

---

## 🎉 Get Started

```bash
# One-click Start (using script)
bash scripts/setup.sh

# Or Manual Start
npm install
npm run db:generate
npm run db:push
npm run dev
```

**Enjoy! 🚀**