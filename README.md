# Line Queue PR Agent

An intelligent, AI-powered Pull Request review agent designed to streamline your code review process. By leveraging vector embeddings and advanced LLMs, Line Queue PR Agent understands the full context of your repository to provide insightful, accurate, and constructive feedback on Pull Requests.

## 🚀 Features

-   **🤖 AI-Powered Code Analysis**: Automatically analyzes Pull Requests to detect potential bugs, security vulnerabilities, and code style issues.
-   **🧠 Deep Context Awareness**: Uses **Pinecone** vector database to store and retrieve repository context, ensuring reviews understand the broader codebase, not just the changed lines.
-   **⚡ Real-time & Background Processing**: Built with **Inngest** to handle complex, long-running workflows like repository indexing and multi-file analysis reliably in the background.
-   **🔐 Seamless Authentication**: Integrated with **Better Auth** for secure GitHub OAuth authentication.
-   **📊 Interactive Dashboard**: A comprehensive dashboard built with **Next.js** and **Shadcn/UI** to track repositories, view reviews, and manage your account.
-   **🔄 Automated Syncing**: Keeps your repository knowledge base up-to-date with the latest changes from GitHub.

## 🛠️ Tech Stack

-   **Framework**: [Next.js 16 (App Router)](https://nextjs.org/)
-   **Language**: [TypeScript](https://www.typescriptlang.org/)
-   **Database**: [PostgreSQL](https://www.postgresql.org/) & [Prisma ORM](https://www.prisma.io/)
-   **Vector DB**: [Pinecone](https://www.pinecone.io/)
-   **Job Queue**: [Inngest](https://www.inngest.com/)
-   **AI Integration**: [Vercel AI SDK](https://sdk.vercel.ai/) & [Google Gemini](https://deepmind.google/technologies/gemini/)
-   **Styling**: [Tailwind CSS](https://tailwindcss.com/) & [Shadcn/UI](https://ui.shadcn.com/)
-   **Authentication**: [Better Auth](https://www.better-auth.com/)

## 📂 Project Structure

```
src/
├── app/          # Next.js App Router pages and API routes
├── components/   # Reusable UI components
├── inngest/      # Background job definitions (workflows)
├── lib/          # Core utilities (database, auth, API clients)
├── module/       # Feature-specific logic (e.g., auth, parsing)
└── utils/        # Helper functions
```

## 🏁 Getting Started

Follow these steps to set up the project locally.

### Prerequisites

-   **Node.js** (v18+ recommended)
-   **PostgreSQL** database
-   **Pinecone** account and index

### Installation

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/ronitrai27/Line-Queue-PR-Agent.git
    cd Line-Queue-PR-Agent
    ```

2.  **Install dependencies:**
    ```bash
    npm install
    # or
    yarn install
    # or
    pnpm install
    # or
    bun install
    ```

3.  **Set up Environment Variables:**
    Create a `.env` file in the root directory and add the following variables:

    ```env
    # Database
    DATABASE_URL="postgresql://user:password@localhost:5432/your_db"

    # Authentication (Better Auth & GitHub)
    BETTER_AUTH_SECRET="your_generated_secret"
    BETTER_AUTH_URL="http://localhost:3000"
    GITHUB_CLIENT_ID="your_github_client_id"
    GITHUB_CLIENT_SECRET="your_github_client_secret"

    # AI & Vector DB
    GOOGLE_GENERATIVE_AI_API_KEY="your_gemini_api_key"
    PINECONE_API_KEY="your_pinecone_api_key"
    PINECONE_INDEX="your_index_name"

    # Inngest
    INNGEST_EVENT_KEY="local"
    INNGEST_SIGNING_KEY="local"
    ```

4.  **Initialize the Database:**
    ```bash
    npx prisma migrate dev
    ```

5.  **Run the Development Server:**
    ```bash
    npm run dev
    ```

6.  **Start the Inngest Dev Server (for background jobs):**
    ```bash
    npm run inngest:dev
    ```

    Open [http://localhost:3000](http://localhost:3000) for the app and [http://localhost:8288](http://localhost:8288) for the Inngest dashboard.

## 🤝 Contributing

Contributions are welcome! Please open an issue or submit a Pull Request.

## 📄 License

This project is licensed under the [MIT License](LICENSE.md).
