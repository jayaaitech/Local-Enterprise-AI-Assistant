# 🧠 Local Enterprise AI Assistant

A **privacy-first Enterprise AI Assistant** built with **FastAPI**, **Ollama**, and **ChromaDB** that runs completely offline. The application enables local LLM chat, document-based question answering (RAG), speech-to-text, and text-to-speech without requiring cloud AI services or API keys.

---

## 🚀 Features

- 🤖 Local LLM chat using Ollama
- 📄 Retrieval-Augmented Generation (RAG) over PDF documents
- 🔍 Semantic search powered by ChromaDB
- 🧩 Local embeddings using `nomic-embed-text`
- 🎤 Offline Speech-to-Text using Faster-Whisper
- 🔊 Offline Text-to-Speech using pyttsx3
- ⚡ REST APIs built with FastAPI
- 🛡️ Basic prompt guardrails
- 📝 Conversation logging
- 🔒 Fully offline and privacy-focused

---

## 🏗️ Tech Stack

| Category | Technologies |
|----------|--------------|
| Backend | FastAPI, Python, Uvicorn |
| LLM | Ollama, Llama 3.1 |
| RAG | ChromaDB |
| Embeddings | nomic-embed-text |
| Speech | Faster-Whisper, pyttsx3 |
| Utilities | Pydantic, python-dotenv |

---

# 📂 Project Structure

```
Local-Enterprise-AI/
│
├── app/
│   ├── ai/
│   │   ├── ollama_client.py
│   │   └── prompts.py
│   │
│   ├── rag/
│   │   ├── ingest.py
│   │   ├── store.py
│   │   └── textsplits.py
│   │
│   ├── voice/
│   │   ├── stt.py
│   │   └── tts.py
│   │
│   ├── web/
│   ├── config.py
│   ├── security.py
│   └── main.py
│
├── requirements.txt
├── README.md
└── .gitignore
```

---

# ✨ Features

### 💬 Local Chat

- Runs completely offline
- No OpenAI API Key required
- No cloud dependency
- Uses Ollama locally

---

### 📄 Document Question Answering

1. Place PDFs inside

```
data/docs/
```

2. Click **Ingest Docs**

3. Ask questions about your documents.

---

### 🎤 Speech-to-Text

Uses **Faster-Whisper** for accurate offline voice recognition.

---

### 🔊 Text-to-Speech

Uses **pyttsx3** for offline voice responses.

---

### 🛡️ Guardrails

Includes basic:

- Prompt filtering
- Conversation logging
- Safe response handling

---

# ⚙️ Installation

## 1. Install Python

Python **3.10+**

---

## 2. Install FFmpeg

```powershell
winget install Gyan.FFmpeg
```

Verify:

```powershell
ffmpeg -version
```

---

## 3. Install Ollama

Download from:

https://ollama.com

Pull the required models:

```bash
ollama pull llama3.1:8b-instruct-q4_K_M

ollama pull nomic-embed-text
```

---

## 4. Create Virtual Environment

```powershell
python -m venv .venv

.\.venv\Scripts\activate
```

---

## 5. Install Dependencies

```bash
pip install -r requirements.txt
```

---

## 6. Configure Environment

Copy

```
.env.example
```

to

```
.env
```

Modify values if required.

---

## 7. Run the Application

```bash
uvicorn app.main:app --reload --port 8001
```

Open:

```
http://127.0.0.1:8001
```

---

# 📖 Usage

### Step 1

Place PDF files inside

```
data/docs/
```

### Step 2

Click **Ingest Docs**

### Step 3

Start chatting or use voice input.

---

# 🔗 API Endpoints

| Method | Endpoint | Description |
|---------|----------|-------------|
| POST | `/chat` | Chat with the assistant |
| POST | `/ingest` | Index PDF documents |
| POST | `/transcribe` | Speech-to-text |
| POST | `/speak` | Text-to-speech |
| GET | `/health` | Health check |

---

# 🏛️ Architecture

```
              Web Interface
                    │
                    ▼
             FastAPI Backend
                    │
      ┌─────────────┼─────────────┐
      │             │             │
      ▼             ▼             ▼
   Ollama       ChromaDB      Whisper
   (LLM)         (RAG)          (STT)
      │                           │
      └─────────────┬─────────────┘
                    ▼
             Response Generator
                    │
                    ▼
                 pyttsx3
                  (TTS)
```

---

# 📸 Screenshots

Add screenshots here.

Example:

```
screenshots/home.png

screenshots/chat.png

screenshots/rag.png
```

---

# 🚀 Future Improvements

- Streaming responses
- Conversation memory
- Hybrid search (BM25 + Vector)
- Docker support
- User authentication
- Multi-user support
- GPU acceleration
- Multi-model support

---

# 👩‍💻 Author

**Jaya **

AI Software Developer

**Skills**

- Python
- FastAPI
- RAG
- Ollama
- ChromaDB
- AI Backend Development

GitHub:
https://github.com/Jayasingh174


---
