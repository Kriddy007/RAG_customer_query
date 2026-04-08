# Conversational RAG Agent

A conversational AI agent that answers questions from a document using RAG (Retrieval Augmented Generation), built with LangChain, Groq, and ChromaDB.

## What it does
- Loads a document and splits it into chunks
- Converts chunks into vector embeddings for semantic search
- Retrieves relevant chunks based on the user's question
- Answers using only the document content — no hallucination
- Maintains conversation history for follow-up questions

## RAG Pipeline
Question → Retriever → Relevant Chunks → LLM → Answer

## Tech Stack
| Component | Tool |
|---|---|
| LLM | Groq (llama-3.1-8b-instant) |
| Embeddings | sentence-transformers/all-MiniLM-L6-v2 |
| Vector Store | ChromaDB |
| Framework | LangChain |

## Setup
pip install langchain langchain-groq langchain-community langchain-chroma langchain-huggingface langchain-text-splitters chromadb sentence-transformers

Add your Groq API key in the LLM setup cell. Get a free key at https://console.groq.com

## Key Concept
The agent only answers from the provided document. If the answer is not in the document it says so — this prevents the LLM from making things up.
