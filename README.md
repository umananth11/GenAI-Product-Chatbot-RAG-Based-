# 🧠 GenAI Product Chatbot (RAG-Based)

A **Generative AI–powered Product Clarification Chatbot** built using **Retrieval-Augmented Generation (RAG)** over a real **Flipkart product catalogue**, combined with **LoRA-based LLM fine-tuning** for improved instruction following and response consistency.  
The chatbot answers product-related questions using **retrieved catalogue knowledge**, ensuring **fact-based, low-hallucination, and context-aware responses**..

---

## 🚀 Features

- Product catalogue–aware chatbot
- Retrieval-Augmented Generation (RAG)
- FAISS-based semantic search
- LoRA fine-tuned LLM (instruction alignment)
- FastAPI backend (`/chat` endpoint)
- Public API access using Cloudflare Tunnel
- Streamlit chat interface
- Input validation and safe error handling

---

## 🧩 Problem Statement

Customer support teams and distributors need quick and accurate clarification on product features, specifications, and pricing.  
Traditional chatbots often hallucinate responses or rely on static rules.

This project solves the problem by dynamically injecting product catalogue knowledge into the LLM using **RAG**, ensuring reliable answers.

---

## 🏗️ Architecture

User Query
↓
Sentence Embedding
↓
FAISS Vector Search
↓
Relevant Product Context
↓
LoRA-Fine-Tuned LLM (Mistral)
↓
Grounded Response

---

## 📊 Dataset

- **Flipkart Products Dataset** (Kaggle)
- Key fields used:
  - product_name
  - brand
  - product_category_tree
  - price
  - description

Each product is converted into a structured text document and indexed for semantic retrieval.

---

## 🛠️ Tech Stack

| Layer | Technology |
|------|-----------|
| LLM | Mistral-7B-Instruct |
| Fine-Tuning | LoRA (PEFT) |
| Embeddings | Sentence-Transformers |
| Vector Store | FAISS |
| Backend API | FastAPI |
| Public Access | Cloudflare Tunnel |
| Frontend | Streamlit |
| Environment | Google Colab |

---

## 🔄 How It Works

1. Product catalogue data is cleaned and converted into documents  
2. Documents are embedded and stored in FAISS  
3. User query is embedded and matched with relevant products  
4. Retrieved context is injected into the LLM prompt  
5. LLM generates a grounded response  
6. Response is served via FastAPI and consumed by Streamlit UI  

---

## 🔌 API Usage

### POST `/chat`

**Request**
```json
{
  "question": "Is this phone good for battery life?"
}
{
  "answer": "Based on the product catalogue, this phone offers a high-capacity battery suitable for daily usage."
}
## 📓 Notebook

The complete end-to-end implementation is available as a Jupyter/Colab notebook:

- **GEN_AI_Chatbot.ipynb** – Data preparation, FAISS indexing, RAG pipeline, LoRA fine-tuning, FastAPI backend, and Streamlit UI

You can run the notebook locally or in Google Colab for quick experimentation and demos.
