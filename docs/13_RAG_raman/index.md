# 💡 Carbon Nanotubes RAG System

**Semantic search engine for scientific research using Retrieval-Augmented Generation**

## 🎯 Overview

A full-stack RAG application that enables semantic search across 27 scientific papers on Raman spectroscopy and carbon nanotube nanostructures. Users can ask natural language questions and receive AI-generated answers backed by real scientific sources.

![Top 20 Consumers](zdi1.png)

## 🚀 Features

- **Semantic Search** - FAISS vector similarity on 3,400+ document chunks
- **AI-Powered Answers** - OpenAI GPT-4o-mini generates responses from retrieved context
- **Source Citation** - Every answer includes relevant source fragments with relevance scores
- **PDF Filtering** - Select specific papers to focus retrieval
- **Keyword Highlighting** - Real-time TF-IDF keyword extraction
- **Live Demo** - Deployed on Streamlit Community Cloud

## 🛠️ Tech Stack

- **Backend**: Python, FAISS, Sentence Transformers, OpenAI API
- **Frontend**: Streamlit
- **Deployment**: Streamlit Community Cloud
- **Data**: 27 scientific PDFs (~3,400 chunks)

## 📊 How It Works
```
User Question
    ↓
Embedding (384D vector)
    ↓
FAISS Search (top 5 similar chunks)
    ↓
Context Augmentation
    ↓
GPT-4o-mini Generation
    ↓
Answer + Sources
```

## 🔗 Links

- <a href="https://carbon-nanotubes-rag.streamlit.app" target="_blank">Live App</a>
- <a href="https://github.com/slastrzelec/13_rag_raman_carbon_nanotubes" target="_blank">GitHub Repository</a>

## 📈 Results

- Deployed live application
- Processes 27 scientific papers
- ~10-15 second response time
- 384-dimensional semantic embeddings
- Free Streamlit Cloud hosting