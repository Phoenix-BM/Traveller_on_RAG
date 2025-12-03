# 🌍 Intelligent Travel Guide Q&A System

> An intelligent travel assistant powered by Retrieval-Augmented Generation (RAG) and Large Language Models.

[![Python](https://img.shields.io/badge/Python-3.9%2B-blue)](https://www.python.org/)
[![LangChain](https://img.shields.io/badge/LangChain-Framework-green)](https://www.langchain.com/)
[![GLM-4](https://img.shields.io/badge/LLM-GLM--4-purple)](https://github.com/THUDM/GLM-4)

## 📖 Introduction

This project implements a vertical domain **Question-Answering System for Travel Strategies**, leveraging the power of **RAG (Retrieval-Augmented Generation)** and the **GLM-4** model.

By ingesting real-world travel data from **Xiaohongshu**, the system solves the problem of hallucination in general LLMs when dealing with specific, up-to-date travel queries. It offers a conversational interface to help users plan trips with verified, community-driven advice.

## 🚀 Key Features

### 1. Large-Scale Data Construction
- Built a robust crawler system using **Selenium**.
- Successfully scraped and cleaned **20,000+** travel strategy entries from dynamic web pages on Xiaohongshu.
- Constructed a specialized vector knowledge base for travel recommendations.

### 2. Modular RAG Pipeline
- Designed a scalable **five-layer architecture**:
  - **Data Layer:** ETL processes for unstructured text.
  - **Database Layer:** Vector storage (e.g., ChromaDB/Milvus).
  - **Application Layer:** Retrieval logic and prompt engineering.
  - **LLM Layer:** Integration with GLM-4 via API.
  - **Service Layer:** API endpoints and frontend logic.
- Implemented **LangChain** for orchestration.
- Optimized retrieval using **Maximum Marginal Relevance (MMR)** to ensure diverse and precise context retrieval, preventing repetitive information.

### 3. Interactive Multi-Turn Dialogue
- Deployed a web-based chat interface using **Gradio**.
- Enabled **context-aware interactions**: The system intelligently fuses historical queries with current inputs to handle multi-turn conversations effectively (e.g., "Recommend a hotel there" understands "there" refers to the previously mentioned city).

<img width="1335" height="628" alt="image" src="https://github.com/user-attachments/assets/3e29b2c3-b769-4f06-a100-fac5fc8fa21a" />


## 🛠️ Architecture

The system follows a standard RAG workflow:
1. **Query Rewriting:** Enhances user input with conversation history.
2. **Retrieval:** Fetches relevant documents from the vector store using MMR.
3. **Augmentation:** Constructs a prompt with the retrieved context.
4. **Generation:** GLM-4 generates the final answer.

<img width="1312" height="695" alt="image" src="https://github.com/user-attachments/assets/b4c7f85e-9c37-4075-9194-1c3e3809bec3" />


## 📚 Acknowledgements & References

This project is inspired by and references the curriculum from **Datawhale**:
- **《[动手学大模型应用开发](https://datawhalechina.github.io/llm-universe/#)》 (Hands-on Large Model Application Development)**

## 📦 Tech Stack

- **LLM:** GLM-4 (Zhipu AI)
- **Framework:** LangChain
- **Embedding:** (Mention your embedding model here, e.g., BGE / OpenAI)
- **Vector DB:** (Mention your DB here, e.g., Chroma / FAISS)
- **Crawler:** Selenium
- **UI:** Gradio
