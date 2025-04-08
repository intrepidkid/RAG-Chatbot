# 🧠 RAG Chatbot – Retrieval-Augmented Generation with LangChain

This is a lightweight, local Retrieval-Augmented Generation (RAG) chatbot built using **LangChain**, **Chroma**, and a **local LLM** (neural-chat 7B GGUF model). It allows users to ask questions, and the system responds with contextually relevant answers based on ingested documents.

## 🚀 Features

- 🔍 **Document Search:** Uses Chroma vector store to find relevant chunks.
- 🧠 **Local LLM:** Uses `CTransformers` to run a GGUF quantized model (no internet required).
- 🧾 **Custom PDF Ingestion:** Load and split PDFs using `PyMuPDFLoader`.
- 🧬 **HuggingFace BGE Embeddings:** For high-quality semantic search.
- 🌐 **Flask Web App:** Simple frontend to interact with the chatbot.

---

## 🗂️ Project Structure

```
RAG_Chatbot_Inv_Bank/
│
├── Data/
│   ├── app.py                  # Main Flask app
│   ├── ingest.py               # For loading and vectorizing documents
│   ├── neural-chat-7b...gguf   # Local quantized LLM (ignored in git)
│   └── 400 Questions.pdf       # Sample document
│
├── templates/
│   └── index.html              # Frontend for the chatbot
│
├── stores/                     # Chroma vector store (ignored in git)
├── .gitignore
└── README.md
```

---

## 🛠️ Installation

> 📍 Make sure you have Python 3.10+ and `pip` installed.

```bash
git clone https://github.com/intrepidkid/RAG-Chatbot-.git
cd RAG-Chatbot-

python -m venv venv
venv\Scripts\activate  # or source venv/bin/activate on Unix

pip install -r requirements.txt
```

> Make sure to download the `.gguf` model file manually and place it inside the `Data/` folder.

---

## ⚙️ Usage

### 1. Ingest Documents

Run this once to process your PDF files and generate embeddings:

```bash
python Data/ingest.py
```

### 2. Start the Flask App

```bash
python Data/app.py
```

Go to `http://127.0.0.1:5000/` to chat!

---

## 🔒 .gitignore Example

```gitignore
venv/
__pycache__/
*.pyc
*.log
.env
*.gguf
stores/
```

---

## 💡 Tech Stack

- [LangChain](https://www.langchain.com/)
- [CTransformers](https://github.com/marella/ctransformers)
- [ChromaDB](https://www.trychroma.com/)
- [HuggingFace BGE Embeddings](https://huggingface.co/BAAI/bge-large-en)
- Flask + HTML

---

## 🧼 TODO

- [ ] Improve UI with streaming response
- [ ] Add file upload functionality
- [ ] Support GPU inference (optional)

---

## 📜 License

MIT License

---

## 🧑‍💻 Author

**@intrepidkid**  
🔗 [GitHub](https://github.com/intrepidkid)
