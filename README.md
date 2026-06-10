# PDF Chat Assistant
I built this to practice RAG (Retrieval Augmented Generation) — 
basically a way to chat with any PDF using an AI model.
You upload a PDF, ask questions about it, and it answers 
based on what's actually in the document. It also remembers 
the last few things you asked so the conversation flows naturally.

## How it works
The PDF gets broken into chunks, converted into vectors using 
HuggingFace embeddings, and stored in a FAISS vector database. 
When you ask a question, it finds the most relevant chunks and 
sends them to Claude along with your question.

## Stack
- LangChain for the pipeline
- HuggingFace sentence-transformers for embeddings
- FAISS for vector storage
- Anthropic Claude Haiku as the LLM

## Setup
1. Clone the repo
2. Install dependencies
   pip install -r requirements.txt
3. Add your Anthropic API key
4. Run the notebook

## Notes
LangChain removed the chains module entirely so the 
usual ConversationalRetrievalChain approach won't work. 
Built a manual pipeline instead which works fine.

## What's next
- Streamlit web UI so anyone can use it without touching code
- Better handling for PDFs with tables and images
