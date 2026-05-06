To include the specific images from your `images` folder in your `README.md`, you should use the standard Markdown image syntax. Since you want to match the structure of your previous template, I have placed each image under its corresponding task description.

```markdown
# ML_WEEK12_B01
# 🚀 intro_to_LLM

> **Name:** Muhammad Fahad
> **Email:** [![Email](https://img.shields.io/badge/Email-mfk21927@gmail.com-red?style=flat-square&logo=gmail&logoColor=white)](mailto:mfk21927@gmail.com)
> **LinkedIn:** [![LinkedIn](https://img.shields.io/badge/LinkedIn-Muhammad%20Fahad-blue?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/muhammad-fahad-087057293)
> **Start Date:** 20-12-2025

---

![Internship](https://img.shields.io/badge/Status-Active-blue?style=for-the-badge)
![Batch](https://img.shields.io/badge/Batch-B01-orange?style=for-the-badge)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-Transformers-yellow?logo=huggingface&logoColor=white)](https://huggingface.co/)
[![Flask](https://img.shields.io/badge/Flask-3.x-black?logo=flask&logoColor=white)](https://flask.palletsprojects.com/)
[![FAISS](https://img.shields.io/badge/FAISS-Vector%20DB-blue?logo=meta&logoColor=white)](https://github.com/facebookresearch/faiss)

---

## 📌 Project Overview

This repository documents my **Week 12 Machine Learning Internship tasks**, focused on building a local **Retrieval-Augmented Generation (RAG) System**. 
It covers the entire pipeline from **vector database initialization and document embedding** to **LLM prompt augmentation and remote Flask deployment** using cloud tunnels.

-----

## 📈 Week 12 Tasks Overview

| Task | Title | Key Tech | Status |
| :--- | :--- | :--- | :--- |
| 12.1 | RAG Models & Vector DB Setup | FAISS, SentenceTransformers, GPT-2 | ✅ Completed |
| 12.2 | Document Processing Pipeline | Text Chunking, Embeddings, Memory Management | ✅ Completed |
| 12.3 | Context-Aware Flask API & UI | Flask, REST APIs, HTML/JS | ✅ Completed |
| 12.4 | Remote Deployment & Tunneling | Cloudflared, Localtunnel, Threading | ✅ Completed |

-----

## ✅ Task Details

### **Task 12.1: RAG Models & Vector DB Setup**
*Initialized the foundational models and the vector database for efficient retrieval.*

![LLM Setup](images/llm_pic.PNG)

*   Initialized a `SentenceTransformer` (`all-MiniLM-L6-v2`) for generating semantic text embeddings.
*   Loaded a local LLM pipeline using HuggingFace's `AutoModelForCausalLM` and `AutoTokenizer` (`GPT-2`).
*   Configured a local **FAISS IndexFlatL2** vector database to store and search 384-dimensional text embeddings in memory.

### **Task 12.2: Document Processing Pipeline**
*Handling semantic search capabilities and document ingestion.*

![Semantic Processing](images/sementic_pic.PNG)

*   Built an `/upload` endpoint to ingest raw `.txt` knowledge files.
*   Implemented a robust text-splitting algorithm using regex to handle variable line breaks and isolate coherent facts.
*   Engineered a hard-reset mechanism (`index.reset()`) to clear the vector DB and corpus on new uploads, preventing data contamination.

### **Task 12.3: Context-Aware Flask API & UI**
*Connecting the RAG components through a user-friendly interface.*

![RAG System](images/rag_pic.PNG)

*   Implemented the RAG retrieval logic: vectorized the user query, performed a similarity search in FAISS, and extracted the top matching chunks.
*   Augmented the LLM prompt with the retrieved background information to generate factual, context-grounded answers.
*   Built an integrated HTML/CSS/JS frontend served directly via Flask to provide a seamless chat interface.

### **Task 12.4: Remote Deployment & Tunneling**
*Deploying the application via API endpoints and secure tunnels.*

![RAG API](images/rag_api_pic.PNG)

*   Configured the Flask application to run safely in a background daemon thread (`0.0.0.0:5000`).
*   Wrote automation to hunt down and kill ghost servers (`fuser -k 5000/tcp`) preventing port collisions.
*   Bypassed VS Code dev tunnel limitations by deploying the local server to the public internet using **Cloudflare Tunnels**.

-----

## 📁 Project Structure
```
intro_to_LLM_w012/
├── images/                  # Task screenshots and diagrams
├── app.py                   # Main RAG pipeline, Flask server, and API logic
├── test_data.txt            # Sample knowledge base for context retrieval
├── requirements.txt         # Project dependencies
└── README.md                # Documentation
```

-----

## 💻 Tech Stack

*   **Machine Learning:** HuggingFace Transformers, SentenceTransformers, FAISS
*   **Frameworks:** Flask
*   **Languages:** Python, JavaScript, HTML/CSS
*   **Networking & Deployment:** Cloudflare Tunnels, Localtunnel, Linux Port Management
```