# RAG Chatbot Workflow

An AI-powered Retrieval-Augmented Generation (RAG) chatbot workflow built using n8n, OpenAI, Supabase Vector Database, and PostgreSQL memory.

This project enables users to upload documents, store them as vector embeddings, and interact with them through a conversational AI assistant capable of semantic search and contextual question answering.

---

# Project Overview

Large Language Models (LLMs) are powerful, but they cannot reliably answer questions about:
- private company documents,
- contracts,
- internal knowledge bases,
- or custom business data.

This project solves that problem using a RAG (Retrieval-Augmented Generation) architecture.

The workflow:
1. Downloads and processes documents
2. Converts text into vector embeddings
3. Stores embeddings in Supabase
4. Retrieves relevant document chunks during chat
5. Generates context-aware AI responses
6. Maintains conversation memory using PostgreSQL

---

# Architecture

```text
                   User
                     │
                     ▼
              Chat Trigger
                     │
                     ▼
                 AI Agent
          ┌──────────┼──────────┐
          ▼          ▼          ▼
      OpenAI      Memory     Vector Search
        LLM      (Postgres)   (Supabase)
                                   │
                                   ▼
                         Relevant Document Chunks
                                   │
                                   ▼
                           AI Generated Answer


Document Ingestion Pipeline
────────────────────────────────

Google Drive File
        │
        ▼
Document Loader
        │
        ▼
OpenAI Embeddings
        │
        ▼
Supabase Vector Database
```

---

# Key Features

## RAG (Retrieval-Augmented Generation)
Retrieves relevant document information before generating responses.

## AI-Powered Document Chat
Ask natural language questions about uploaded documents.

## Semantic Search
Uses vector embeddings to search based on meaning instead of keywords.

## Conversation Memory
Stores chat history using PostgreSQL for contextual conversations.

## Vector Database Integration
Uses Supabase as the vector storage layer.

## Automated Document Processing
Automatically downloads, extracts, embeds, and stores document data.

## Modular Workflow Design
Built using reusable n8n workflow nodes for scalability and flexibility.

---

# Tech Stack

| Component | Technology |
|---|---|
| Workflow Automation | n8n |
| LLM | OpenAI GPT |
| Embedding Model | OpenAI Embeddings |
| Vector Database | Supabase |
| Memory Storage | PostgreSQL |
| Document Source | Google Drive |
| Architecture | RAG (Retrieval-Augmented Generation) |

---

# Workflow Breakdown

# 1. Document Ingestion Pipeline

Responsible for preparing documents for retrieval.

## Steps

### Download File
Downloads documents from Google Drive.

### Document Loader
Extracts text content from uploaded files.

### Embedding Generation
Converts document text into vector embeddings using OpenAI.

### Vector Storage
Stores embeddings inside Supabase for semantic retrieval.

---

# 2. AI Chat Pipeline

Responsible for answering user questions.

## Steps

### Chat Trigger
Starts workflow when a user sends a message.

### AI Agent
Main orchestration component responsible for:
- handling user queries,
- retrieving document context,
- generating final responses.

### PostgreSQL Memory
Maintains conversation history for contextual interactions.

### Supabase Vector Search
Retrieves relevant document chunks using semantic similarity.

### OpenAI Response Generation
Combines retrieved context with the user query to generate accurate responses.

---

# Example Use Cases

- AI Contract Assistant
- Internal Knowledge Base Chatbot
- HR Policy Assistant
- Customer Support AI
- Legal Document Search
- Enterprise Knowledge Retrieval
- PDF Question Answering
- Research Document Assistant

---

# Challenges Solved

## LLM Knowledge Limitation
Enabled AI to answer questions from custom/private documents.

## Semantic Retrieval
Implemented vector search instead of traditional keyword search.

## Context Retention
Added persistent memory using PostgreSQL.

## Modular AI Automation
Built scalable workflow architecture using n8n nodes.

---

# What This Project Demonstrates

This project demonstrates practical understanding of:
- RAG Architecture
- Vector Databases
- Semantic Search
- AI Workflow Automation
- AI Agent Orchestration
- OpenAI Integration
- Supabase Integration
- Memory-Augmented AI Systems
- Enterprise AI Design
- n8n AI Workflows

---

# Author

Sandeep Setty

AI / GenAI / Agentic AI Enthusiast  
Focused on building practical AI systems and workflow automation projects.
