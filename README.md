# 🎥 YouTube Video Chatbot (RAG)

A Retrieval-Augmented Generation (RAG) chatbot that lets you **ask questions about any YouTube video**. It fetches the video's transcript, indexes it in a vector store, and answers your questions using only the video's content.

![Python](https://img.shields.io/badge/python-3.10%2B-blue)
![Jupyter](https://img.shields.io/badge/notebook-Jupyter-orange)
![RAG](https://img.shields.io/badge/approach-RAG-7c3aed)

---

## 📖 Overview

Watching long videos just to find one answer is slow. This project turns a YouTube video into a searchable knowledge base:

1. The transcript is fetched from the video.
2. The text is split into chunks and converted to embeddings.
3. The embeddings are stored in a vector database.
4. Your question retrieves the most relevant chunks, and an LLM generates an answer grounded in them.

---

## ✨ Features

- 🔗 Works with any YouTube video that has captions
- 📝 Automatic transcript extraction
- ✂️ Smart text chunking for better retrieval
- 🔍 Semantic search over the transcript
- 💬 Question answering grounded in the video content
- [Add: summary generation, multi-video support, Streamlit UI, etc., if implemented]

---

## 🧠 How It Works

```
YouTube URL
    │
    ▼
Fetch Transcript        ([youtube-transcript-api / other])
    │
    ▼
Split into Chunks       ([RecursiveCharacterTextSplitter])
    │
    ▼
Create Embeddings       ([OpenAI / HuggingFace / other])
    │
    ▼
Vector Store            ([FAISS / Chroma])
    │
    ▼
Retriever (top-k chunks) ──► LLM ([OpenAI / Mistral / Gemini / other]) ──► Answer
```

---

## 🛠️ Tech Stack

| Category | Technology |
|----------|------------|
| Language | Python 3.10+ |
| Environment | Jupyter Notebook |
| Framework | [LangChain] |
| Transcript | [youtube-transcript-api] |
| Embeddings | [model name] |
| Vector Store | [FAISS / Chroma] |
| LLM | [model name] |

---

## 📂 Project Structure

```
Youtube-Video-Chatbot-RAG-App/
├── chatbot-model.ipynb   # Main notebook: transcript → embeddings → RAG chatbot
├── .gitignore
└── README.md
```

---

## 🚀 Getting Started

### Prerequisites

- Python 3.10 or higher
- Jupyter Notebook / JupyterLab / VS Code
- An API key for your LLM provider [OpenAI / Mistral / Gemini]

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/Jugal1011/Youtube-Video-Chatbot-RAG-App.git
cd Youtube-Video-Chatbot-RAG-App

# 2. Create and activate a virtual environment (recommended)
python -m venv venv
source venv/bin/activate        # Linux / macOS
venv\Scripts\activate           # Windows

# 3. Install dependencies
pip install [youtube-transcript-api langchain langchain-community faiss-cpu python-dotenv jupyter]
```

---

## 💻 Usage

1. Set the **video ID** (the part after `v=` in the YouTube URL) in the notebook.
2. Run the cells to fetch the transcript and build the vector store.
3. Ask questions in the chat cell, for example:
   - *"What is this video about?"*
   - *"Summarise the key points."*
   - *"What did the speaker say about [topic]?"*

---

## ⚠️ Limitations

- Only works for videos with available captions/transcripts.
- Answers are limited to what the transcript contains.
- Very long videos may need chunk size or `k` tuning for best results.

---

## 🔮 Future Improvements

- Streamlit / web interface
- Chat memory for follow-up questions
- Timestamps and source links in answers
- Support for multiple videos and playlists
- Multilingual transcripts

---

## 👤 Author

**Jugal**
- GitHub: [@Jugal1011](https://github.com/Jugal1011)
