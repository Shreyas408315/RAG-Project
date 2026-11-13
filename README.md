# RAG-Based Question Answering System

A simple Retrieval-Augmented Generation (RAG) application built using **Python, Sentence Transformers, NumPy, and Groq API**. The project retrieves relevant information from a predefined collection of documents using semantic similarity and generates context-aware answers using a Large Language Model (LLM).

## 🚀 Project Overview

This project demonstrates the fundamental workflow of a RAG pipeline, where an LLM generates answers based on retrieved document context rather than relying entirely on its pre-trained knowledge.

The current implementation uses employee policy documents as its knowledge base, allowing users to ask questions about company policies such as paid leave, work-from-home schedules, reimbursements, and notice periods.

## 🏗️ Architecture

```text
             Documents
                 |
                 v
         Sentence Transformer
                 |
                 v
          Document Embeddings
                 |
                 v
             NumPy
          (Vector Storage)
                 |
                 v
          User Query
                 |
                 v
          Query Embedding
                 |
                 v
        Cosine Similarity
                 |
                 v
       Relevant Document
                 |
                 v
          Groq LLM API
                 |
                 v
          Final Answer
```

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| Python | Core programming language |
| Sentence Transformers | Generating text embeddings |
| all-MiniLM-L6-v2 | Embedding model |
| NumPy | Vector operations and similarity calculation |
| Groq API | LLM inference |
| GPT-OSS 120B | Answer generation |
| python-dotenv | Environment variable management |

## ⚙️ Features

- **Semantic Search:** Converts documents and user queries into numerical embeddings.
- **Cosine Similarity:** Measures semantic similarity between query and document embeddings.
- **Context Retrieval:** Retrieves the most relevant document for a given query.
- **LLM Integration:** Uses Groq API to generate natural-language responses.
- **Context-Grounded Generation:** Instructs the LLM to answer using retrieved context to reduce hallucinations.

## 📂 Project Structure

```text
RAG-Project/
│
├── full_rag.py
├── main.py
├── .env
├── .gitignore
├── pyproject.toml
└── README.md
```

## 🔧 Installation and Setup

### 1. Clone the repository

```bash
git clone <your-repository-url>
cd RAG-Project
```

### 2. Create a virtual environment

```bash
python -m venv .venv
```

Activate it:

**Windows:**
```bash
.venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install groq numpy python-dotenv sentence-transformers
```

### 4. Configure environment variables

Create a `.env` file in the project root:

```env
GROQ_API_KEY=your_groq_api_key
```

Get your API key from [Groq Console](https://console.groq.com/).

### 5. Run the application

```bash
python full_rag.py
```

## 💡 Example

**Input Query:**
```text
How much vacation do I get?
```

**Retrieved Context:**
```text
Employees receive 24 days of paid leave per year.
```

**Generated Answer:**
```text
You get 24 days of paid leave per year.
```

## 🧠 Core Concepts Implemented

1. Text Embeddings
2. Semantic Search
3. Vector Representations
4. Cosine Similarity
5. Document Retrieval
6. Retrieval-Augmented Generation
7. Prompt Engineering
8. LLM API Integration

## 🔮 Future Improvements

- Implement Top-K document retrieval.
- Introduce document chunking and chunk overlap.
- Integrate a vector database such as FAISS or ChromaDB.
- Support PDF and text document ingestion.
- Implement conversation history.
- Add a Streamlit-based user interface.
- Experiment with different embedding models and retrieval strategies.

## 📌 Learning Objective

This project is part of my journey toward understanding and building Generative AI applications. It focuses on implementing the fundamentals of Retrieval-Augmented Generation and understanding how semantic retrieval and LLMs work together to generate context-aware answers.