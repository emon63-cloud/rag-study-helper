# RAG Study Helper

An AI study assistant that answers questions and makes quizzes **from your own study material** (PDF books and notes), using Retrieval-Augmented Generation (RAG).

## Features

- **Upload PDFs** – books are split into chunks, embedded, and saved in a vector database
- **Ask (chat)** – ask questions and get answers based only on your notes, with page numbers
- **Follow-up questions** – the chat remembers earlier messages
- **Hybrid search** – combines exact keyword matching with meaning-based search
- **Quiz mode** – MCQ, True/False or mixed questions, with scoring and explanations

## How it works

```
PDF → extract text → split into chunks → embeddings → ChromaDB
Question → embed → find closest chunks → chunks + question → LLM → answer / quiz
```

## Tech stack

| Part | Tool |
|------|------|
| UI | Streamlit |
| PDF reading | pypdf |
| Embeddings | sentence-transformers (`all-MiniLM-L6-v2`) |
| Vector database | ChromaDB |
| LLM | Groq API (`openai/gpt-oss-120b`) |

## Run it locally

1. Clone this repo and open the folder.
2. Create and activate a virtual environment:
   ```
   python -m venv venv
   venv\Scripts\activate
   ```
3. Install the packages:
   ```
   pip install -r requirements.txt
   ```
4. Create a file named `.env` with your Groq API key:
   ```
   GROQ_API_KEY=your_key_here
   ```
5. Start the app:
   ```
   streamlit run app.py
   ```
