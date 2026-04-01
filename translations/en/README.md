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

Let me translate this document:

The document is about a GitHub repository AI documentation translation platform. Let me translate it section by section, preserving all formatting.

Key things to translate:
- Headers
- Body text
- List items (translate the content, keep the numbering)
- Comments in code blocks (like "# 创建数据库（MySQL 命令行）")

Things NOT to translate:
- Code snippets
- URLs
- File paths like `./docs/本地运行指南.md`
- Variable names and values in code blocks
- Technical identifiers

Let me start translating:
</think>

# GitHub Repository AI Documentation Translation Platform

> Author: [Programmer Yupi](https://yuyuanweb.feishu.cn/wiki/Abldw5WkjidySxkKxU2cQdAtnah)
>
> This is a teaching project that provides complete video tutorials + text tutorials + resume writing + interview question solutions + Q&A services to help you improve your project skills and add highlights to your resume!
>
> ⭐️ Join the project series learning: [Join Programming Navigator](https://www.codefather.cn/vip)



## 1. Project Introduction

This is a project tutorial centered on **AI Programming Practice**, based on Next.js + GitHub App + OpenRouter. Using AI programming, develop a "GitHub Repository AI Documentation Translation SaaS Platform" from 0 to 1, taking you through the complete workflow of AI Vibe Coding, and teaching you how to create products that are truly usable, deployable, and profitable!

📺 Project introduction video, quickly view the finished product: https://bilibili.com/video/BV1mAAmzqEfP

![](https://pic.yupi.icu/1/1769079083162-aa879560-6044-4ef7-a3a2-718b03070978-20260225143424199.png)

Enter any GitHub repository address, and AI will automatically translate the documentation into multiple languages. When the base language content changes, it will **automatically incrementally synchronize the translation** and generate a PR waiting for the repository maintainer to merge, requiring no manual intervention throughout the entire process.



### Why This Project?

Yupi open-sourced an AI programming tutorial repository [ai-guide](https://github.com/liyupi/ai-guide), which contains hundreds of Chinese tutorial documents. To allow overseas users to also view it, we wanted to translate the repository into multiple language versions, but manual translation costs are too high, and GitHub Actions requires configuring it yourself...

Since that's the case, **let's make a more general-purpose tool**.

This is the starting point of the GitHub Global project: enter any GitHub repository address, and AI will automatically translate the documentation into multiple languages. When the base language content changes, it will **automatically incrementally synchronize the translation** and generate a PR waiting for the repository maintainer to merge, requiring no manual intervention throughout the entire process.

Zero configuration, one-click translation, take your GitHub project global!

![](https://pic.yupi.icu/1/GitHub%2520Global%2520%25E4%25B8%25BB%25E9%25A1%25B5.png)



### 6 Core Features

1) One-click login with GitHub account, implementing secure login and authorization based on GitHub App.

![](https://pic.yupi.icu/1/image-20260225142930323.png)



2) Import GitHub repository, enter the address to automatically pull repository information.

![](https://pic.yupi.icu/1/1769079897565-92698844-bfcc-4f6d-b226-d18352ea2244-20260225144921746-20260225144924730.png)



3) Configure translation, visually select translation scope and target language (supporting 20 mainstream languages).

![](https://pic.yupi.icu/1/1769079897565-92698844-bfcc-4f6d-b226-d18352ea2244-20260225144921746-20260225144924730.png)



4) One-click execute translation, display progress in real-time, automatically create PR after translation is complete.

![](https://pic.yupi.icu/1/1769079926879-90640105-2d23-418c-b4b5-e962eab31299-20260225144931498.png)

![](https://pic.yupi.icu/1/1769080074375-806fa172-c440-47e3-93fd-07ad33c271ea-20260225144935674.png)

Repository maintainers can choose whether to merge this translation themselves, which is both convenient and secure:

![](https://pic.yupi.icu/1/1769080059408-f3e3d44f-df55-4872-8bdc-c781b71cfc81.png)



5) Automatically trigger incremental translation, after enabling, every Push will automatically translate changed documents.

![](https://pic.yupi.icu/1/1770201178863-f4e450bd-b92f-4f56-9b43-82aed36a73b0-20260225142203617.png)

![](https://pic.yupi.icu/1/1770201323050-d991c61a-2ffa-40c1-b1c8-4334ff05c248-20260225141729741.png)



6) Customize large models and API Key, supporting GPT, Claude, Gemini, DeepSeek and other mainstream models.

![](https://pic.yupi.icu/1/1770194573295-9e7552ca-b0c1-4612-a590-6060b5717d79-20260225144945946.png)



## 2. Project Advantages

This project has a novel topic, keeping up with the AI programming era, oriented towards **real SaaS product development**, distinguishing it from the common CRUD projects. The project content is refined, **can be completed in less than a week**, teaching you the complete workflow of AI programming, significantly increasing competitiveness for your resume and job hunting!

Rich technology, covering the entire AI programming chain:

![](https://pic.yupi.icu/1/image-20260225140224582.png)

From this project you can learn:

- How to use AI for requirement research and generate professional "Requirement Specification Documents"?
- How to use multi-AI parallel approach to develop frontend and backend simultaneously?
- How to integrate with GitHub App to implement secure OAuth authorization and repository operations?
- How to integrate with OpenRouter to uniformly connect to hundreds of AI large models?
- How to use GitHub API to get repository file tree, submit files, and create PRs?
- How to implement event-driven automated translation through GitHub Webhook?
- How to use intranet penetration tools to debug Webhook callbacks locally?
- How to deploy Next.js full-stack projects with Vercel for quick launch?
- How to perform code review, version control, and problem fixing in the AI development process?
- How to identify competitor differentiation opportunities and design truly competitive products?




### Yupi Project Series Advantages

Yupi's original projects focus on **practice**, using **live streaming throughout** to build projects **from 0 to 1**. From requirement analysis, technology selection, project design, project initialization, Demo writing, frontend and backend development implementation, project optimization, deployment and launch, etc., I explain every环节 **from theory to practice** clearly, not missing any details!

Compared to learning from online tutorials, the advantages of the Yupi's project series: a one-stop service from learning knowledge => practicing projects => reviewing notes => project Q&A => resume writing => interview question solutions

![](https://pic.yupi.icu/1/image-20260225142355401.png)

Programming Navigator already has **20+ project tutorials!** Each project has different learning focuses, almost all of which are frontend + backend **full-stack projects**, as well as a large number of AI application development projects.

See details: [https://codefather.cn/course](https://www.codefather.cn/course) (There are tutorial recommendations and learning suggestions on the right side of this page)

Previous project introduction videos: [https://bilibili.com/video/BV1YvmbYbEgS](https://www.bilibili.com/video/BV1YvmbYbEgS/)

Yupi's projects have helped many students get high-salary offers from top companies:

![](https://pic.yupi.icu/1/%E7%BC%96%E7%A8%8B%E5%AF%BC%E8%88%AA2026%20offer%E6%8A%A5%E5%96%9C.png)



## 3. More Introduction

Functional Modules:

![](https://pic.yupi.icu/1/image-20260225140201706.png)

Architecture Design:

![](https://pic.yupi.icu/1/image-20260225141302579.png)



## 4. Quick Start

> For detailed step-by-step tutorials, please refer to [Local Running Guide](./docs/本地运行指南.md)

### Prerequisites

- Node.js >= 20
- MySQL >= 8.0
- A [GitHub App](https://github.com/settings/apps/new) (for login and repository operations)
- An [OpenRouter API Key](https://openrouter.ai/keys) (for AI translation)

### 1. Clone and Install Dependencies

```bash
git clone https://github.com/liyupi/github-global.git
cd github-global
npm install
```

### 2. Configure Environment Variables

```bash
# Create environment variable files (keep the content consistent between the two files)
cp .env.example .env
cp .env.example .env.local
```

Edit `.env` and `.env.local`, fill in your configuration:

```bash
DATABASE_URL=mysql://root:your_password@localhost:3306/github_global
NEXTAUTH_URL=http://localhost:3123
AUTH_SECRET=random_string_at_least_32_characters
GITHUB_APP_ID=your_AppID
GITHUB_APP_CLIENT_ID=your_ClientID
GITHUB_APP_CLIENT_SECRET=your_ClientSecret
GITHUB_APP_PRIVATE_KEY_PATH=./private-key.pem
PLATFORM_OPENROUTER_API_KEY=sk-or-v1-your_key
```

Save the GitHub App's private key file as `private-key.pem` in the project root directory.

### 3. Initialize Database and Start

```bash
# Create database (MySQL command line)
mysql -u root -p -e "CREATE DATABASE github_global CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;"

# Generate Prisma client + create tables
npx prisma generate
npx prisma db push

# Start development server
npm run dev
```

Visit **http://localhost:3123** to use.

### Docker Deployment

```bash
docker-compose up -d
docker-compose exec app npx prisma db push
```

For more details, please check [Local Running Guide](./docs/本地运行指南.md) and [Manual Configuration Document](./docs/人工配置文档.md).



## Join Project Learning

Programming Navigator already has **20+ project tutorials!** Each project has different learning focuses, almost all of which are frontend + backend **full-stack** projects, as well as a large number of AI application development projects.

![](https://pic.yupi.icu/1/%25E9%25A1%25B9%25E7%259B%25AE%25E6%2595%2599%25E7%25A8%258B.png)

Welcome to join [Programming Navigator](https://www.codefather.cn/vip). After joining, you can not only follow this project throughout, but also have unlimited access to replay **20+ original project tutorials**. You can also enjoy more original technical materials, learning and job hunting guidance, and hundreds of interview replay videos to start your programming takeoff journey~

🧧 Support the new project learning, we are giving out **limited-time Programming Navigator coupons**, scan the code to get the coupon and join. If you are not satisfied within three days of joining, you can get a full refund. Welcome to join and experience, limited spots, come learn quickly!

<img width="404" alt="image" src="https://github.com/user-attachments/assets/56411098-b60e-4267-8ba2-4ebc5d416afc" />

Less than 1 yuan per day, definitely the most worthwhile investment in yourself! After becoming a Programming Navigator member, you can unlock tutorials and materials for 20+ projects, and learn on both PC website and APP, as shown in the figure:

![](https://pic.yupi.icu/1/image-20250120113756426-20250422160856746.png)