# 🚕 Ride App Support Chatbot

[![Python](https://img.shields.io/badge/Python-3.11-blue?logo=python)](https://www.python.org/)
[![Streamlit](https://img.shields.io/badge/Streamlit-Frontend-orange?logo=streamlit)](https://streamlit.io/)
[![FastAPI](https://img.shields.io/badge/FastAPI-Backend-green?logo=fastapi)](https://fastapi.tiangolo.com/)
[![FAISS](https://img.shields.io/badge/FAISS-VectorSearch-purple)](https://github.com/facebookresearch/faiss)
[![License](https://img.shields.io/badge/License-MIT-blue)](LICENSE)

**AI-powered chatbot for ride-sharing apps using LLMs + RAG for policy-grounded answers.**

---

## 🛠 Features

- **Multi-backend LLM support**  
  - Ollama (`phi3:mini`)  
  - Local LLaMA/llama_cpp (GGUF models)  
  - Google Gemini (via GenAI API)

- **Retrieval-Augmented Generation (RAG)**  
  - FAISS + SentenceTransformers (`all-MiniLM-L6-v2`) for embedding policy documents  
  - Answers are **grounded in fare and ride policies**

- **Interactive Frontend**  
  - Streamlit-based UI  
  - Dynamic backend selection  
  - Expander view for retrieved context

- **Modular & Extensible**  
  - Separate modules for LLMs, RAG, and prompts  
  - Easy to add new LLMs or datasets

---

## 💡 Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | Streamlit |
| Backend | FastAPI |
| LLM Integration | Ollama, LLaMA (llama_cpp), Google Gemini GenAI |
| RAG | FAISS, SentenceTransformers |
| Deployment | Python 3.11+, REST API |

---

## ⚡ Quick Start

### 1️⃣ Clone the repo
```bash
git clone https://github.com/yourusername/ride-app-support-chatbot.git
cd ride-app-support-chatbot
```

### 2️⃣ Install dependencies
```bash
pip install -r requirements.txt
```

### 3️⃣ Set environment variables
Create config.py:
```bash
LOCAL_MODEL_PATH=models/phi-3.gguf
GEMINI_API_KEY=your_gemini_api_key
DEFAULT_LLM_BACKEND=ollama
```

### 4️⃣ Run the app
```bash
uvicorn server:app --reload
streamlit run app.py
```

✅ The chatbot will automatically retrieve relevant context and generate policy-grounded answers.


## 📂 Project Structure
```
.
├── app.py              # Streamlit frontend
├── server.py           # FastAPI backend
├── llm.py              # LLM abstraction (Ollama, local, Gemini)
├── rag.py              # FAISS-based retrieval
├── ingest.py           # Build embeddings/index (runs automatically if needed)
├── prompts.py          # Prompt builder for RAG + LLM
├── data/
│   └── fare_policy.txt
├── index/              # FAISS index + serialized docs
├── models/             # Local LLaMA models (GGUF)
├── config.py           # Default configuration
├── requirements.txt
└── README.md
```


## 🎯 How It Works

  - User input: Frontend sends query + backend selection.

  - RAG retrieval: FAISS returns relevant policy chunks.

  - Prompt building: Retrieved context + user query form LLM prompt.

  - LLM response: Selected LLM generates answer.

  - Context display: UI shows answer + retrieved context in expander.


## 🌟 Skills Demonstrated

  - Multi-LLM integration (local & cloud)
  
  - Retrieval-Augmented Generation (RAG)
  
  - Prompt engineering & LLM orchestration
  
  - FAISS vector search & embedding pipelines
  
  - Full-stack Python (FastAPI + Streamlit)
  
  - Environment & configuration management
  
  - Modular, extensible architecture


## 🔮 Future Improvements

  - Add conversational memory for multi-turn chats
  
  - Support more document types (PDF, CSV, manuals)
  
  - Implement auto-updating FAISS index on new documents
  
  - Deploy as Docker container or cloud app
  
  - Add logging & monitoring for production use


## 📜 License

MIT License © 2026
