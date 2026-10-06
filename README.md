# 🤖 AI Research Assistant

> An AI-powered document research workspace that lets users upload research papers, ask questions about their documents, and receive document-grounded answers through an interactive chat interface.

---

## 📌 Overview

AI Research Assistant is a full-stack AI application designed to make research work faster and more interactive.

Instead of manually searching through long research papers, users can upload a PDF, select the document, and ask questions about its contents through an AI-powered research interface.

The application combines:

- Document upload and management
- User authentication
- Document-grounded question answering
- Semantic embeddings
- Vector-based document retrieval
- Persistent chat history
- React-based research workspace
- FastAPI backend

The project is designed around a retrieval-based AI workflow where relevant document content is retrieved before generating an answer.

---

## ✨ Features

### 🔐 User Authentication

- User login
- Token-based authentication
- Protected document and chat operations
- Logout functionality

### 📄 Document Management

- Upload research papers in PDF format
- View uploaded documents
- Search documents by filename
- Select a document for research
- Delete documents
- Automatically select newly uploaded documents

### 💬 AI Research Chat

- Ask questions about an uploaded research paper
- Receive document-grounded answers
- Maintain chat history for each document
- Continue conversations with previously uploaded documents
- Markdown-formatted AI responses

### 🔎 Semantic Retrieval

The backend uses an embedding-based retrieval workflow to find relevant portions of a document before generating an answer.

This reduces the need to send an entire research paper to the language model for every question.

### 🖥️ Research Workspace

The frontend provides a dedicated workspace containing:

- Document sidebar
- Document search
- PDF upload interface
- Research chat interface
- Chat history
- Document deletion
- User session controls

---

## 🧠 AI / RAG Workflow

The core research flow is conceptually:

```text
                ┌─────────────────────┐
                │     User uploads    │
                │      PDF paper      │
                └──────────┬──────────┘
                           │
                           ▼
                ┌─────────────────────┐
                │   Document parsing  │
                │    and processing   │
                └──────────┬──────────┘
                           │
                           ▼
                ┌─────────────────────┐
                │   Text chunking /   │
                │  document indexing  │
                └──────────┬──────────┘
                           │
                           ▼
                ┌─────────────────────┐
                │   Embedding model   │
                │ (SentenceTransform) │
                └──────────┬──────────┘
                           │
                           ▼
                ┌─────────────────────┐
                │ Semantic retrieval  │
                │ relevant text chunks│
                └──────────┬──────────┘
                           │
          User Question   │
                ┌──────────▼──────────┐
                │   Research Chat     │
                │      Pipeline       │
                └──────────┬──────────┘
                           │
                           ▼
                ┌─────────────────────┐
                │ Document-grounded   │
                │      answer         │
                └─────────────────────┘


AI-Research-Assistant
│
├── frontend/
│   ├── src/
│   ├── components/
│   ├── App.jsx
│   ├── App.css
│   └── package.json
│
├── backend/
│   ├── app/
│   │   ├── config/
│   │   │   └── settings.py
│   │   │
│   │   ├── database/
│   │   │   └── connection.py
│   │   │
│   │   ├── models/
│   │   │   └── document.py
│   │   │
│   │   ├── routes/
│   │   │   ├── auth.py
│   │   │   ├── documents.py
│   │   │   └── chat.py
│   │   │
│   │   ├── services/
│   │   │   ├── chat_service.py
│   │   │   ├── vector_service.py
│   │   │   └── embedding_service.py
│   │   │
│   │   └── main.py
│   │
│   ├── requirements.txt
│   └── .env
│
├── README.md
└── ...
