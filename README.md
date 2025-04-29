### AI-Powered PDF Chatbot

This repository contains the complete architecture for an AI-powered chatbot capable of processing and understanding PDFs with over 100 pages in just seconds.

### Demonstration

![Screenshot_29-Apr_17-40-48_3091](https://github.com/user-attachments/assets/71feee3f-8796-4d32-b282-4131cb05a76c)

![Screenshot_29-Apr_17-40-30_8883](https://github.com/user-attachments/assets/44b54d91-b937-43a2-a17e-fecfd4cfd858)


### Technologies Utilized

- Monorepo (TypeScript Bundled)
- Next.js
- LangChain
- LangGraph
- Gemini
- Supabase

## Setup Instructions

1. **Clone the repository:**

   ```bash
   git clone https://github.com/piyushyadav0191/ai-agent-pdf
   cd ai-agent-pdf
   ```

2. **Install dependencies** from the root directory:

   ```bash
   yarn install
   ```

3. **Set up environment variables** for both the backend and frontend. Refer to the `.env.example` files for guidance.

## Environment Variables

This project requires environment variables for configuration. Each sub-project (backend and frontend) includes a `.env.example` file. Copy these files to `.env` and populate them with your specific details.

### Frontend Environment Variables

Create a `.env` file in the frontend directory:

```bash
cp frontend/.env.example frontend/.env
```

Example variables:

```
NEXT_PUBLIC_LANGGRAPH_API_URL=http://localhost:2024
LANGCHAIN_API_KEY=your-langsmith-api-key-here # Optional: LangSmith API key
LANGGRAPH_INGESTION_ASSISTANT_ID=ingestion_graph
LANGGRAPH_RETRIEVAL_ASSISTANT_ID=retrieval_graph

LANGCHAIN_TRACING_V2=true # Optional: Enable LangSmith tracing

LANGCHAIN_PROJECT="pdf-chatbot" # Optional: LangSmith project name
```

### Backend Environment Variables

Create a `.env` file in the backend directory:

```bash
cp backend/.env.example backend/.env
```

Example variables:

```
OPENAI_API_KEY=your-openai-api-key-here
SUPABASE_URL=your-supabase-url-here
SUPABASE_SERVICE_ROLE_KEY=your-supabase-service-role-key-here

LANGCHAIN_TRACING_V2=true # Optional: Enable LangSmith tracing

LANGCHAIN_PROJECT="pdf-chatbot" # Optional: LangSmith project name
```

**Environment Variable Descriptions:**

- `NEXT_PUBLIC_LANGGRAPH_API_URL`: URL of the LangGraph backend server. Defaults to `http://localhost:2024` for local development.
- `LANGCHAIN_API_KEY`: Optional LangSmith API key for debugging and tracing.
- `LANGGRAPH_INGESTION_ASSISTANT_ID`: ID of the LangGraph assistant for document ingestion. Default: `ingestion_graph`.
- `LANGGRAPH_RETRIEVAL_ASSISTANT_ID`: ID of the LangGraph assistant for question answering. Default: `retrieval_graph`.
- `LANGCHAIN_TRACING_V2`: Enables LangSmith tracing for debugging. Set to `true` to activate.
- `LANGCHAIN_PROJECT`: Name of the LangSmith project.
- `OPENAI_API_KEY`: Your OpenAI API key.
- `SUPABASE_URL`: Your Supabase instance URL.
- `SUPABASE_SERVICE_ROLE_KEY`: Your Supabase service role key.

## Local Development Guide

This monorepo leverages Turborepo to manage both backend and frontend projects. You can run them independently during development.

### Starting the Backend

1. Navigate to the backend directory:

   ```bash
   cd backend
   ```

2. Ensure dependencies are installed (already completed if `yarn install` was run at the root).

3. Launch LangGraph in development mode:

   ```bash
   yarn langgraph:dev
   ```

   This starts a local LangGraph server on port 2024 by default. You can access the LangGraph UI for interaction. Refer to the [LangGraph Studio Guide](https://langchain-ai.github.io/langgraph/concepts/langgraph_studio/) for more details.

### Starting the Frontend

1. Navigate to the frontend directory:

   ```bash
   cd frontend
   ```

2. Start the Next.js development server:

   ```bash
   yarn dev
   ```

   This launches a local Next.js server, typically on port 3000. Access the application in your browser at [http://localhost:3000](http://localhost:3000).

### Contact me incase of problem

For any issues or inquiries, feel free to reach out to me at [piyushyadav0191@gmail.com](mailto:piyushyadav0191@gmail.com).
