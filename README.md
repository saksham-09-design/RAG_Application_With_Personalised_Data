# 🧠 Personalized RAG Chat Application

### *Powered by Ollama, Mistral, Sentence Transformers & ChromaDB*

This project implements a **Retrieval-Augmented Generation (RAG)** pipeline to create a **personalized chat experience**. The system ensures that the model answers **strictly from the context stored in the database**, making it reliable for personalized knowledge bases such as PDFs.

---

## 🚀 Features

* 📄 **Automatic PDF Parsing** using `PyMuPDF (fitz)`
* 🔍 **Vector Embedding Creation** using `all-MiniLM-L6-v2`
* 🧰 **ChromaDB Persistent Vector Store**
* 🤖 **LLM Response Generation** with **Ollama API** and **Mistral model**
* 🎯 **Context-Aware Responses Only**
* 🔗 Modular pipeline for ingestion → embedding → storage → retrieval → generation

---

## 🏗️ Architecture Overview

<img width="2074" height="795" alt="image" src="https://github.com/user-attachments/assets/26ae6759-aa47-412a-a9cb-d4f0660dc5ad" />


1. **PDF Loading**
   PDFs are read using `fitz` and split into clean text chunks.

2. **Embedding Generation**
   Each chunk is converted into a numerical vector using
   ➤ **SentenceTransformer: `all-MiniLM-L6-v2`**

3. **Vector Storage**
   Embeddings + metadata are saved in a persistent **ChromaDB** collection.

4. **Retrieval Pipeline**
   User queries are embedded and matched with the top relevant chunks in the vector store.

5. **LLM Generation (Ollama + Mistral)**
   Retrieved context is passed to **Mistral** (via Ollama API) to generate grounded, contextual responses.

---

## 🛠️ Technologies Used

### **Core Modules**

```python
import requests
import json
import fitz
from sentence_transformers import SentenceTransformer
from chromadb import PersistentClient
```

### **LLM**

* 🌐 **Ollama API**
* 🧠 **Mistral Model**

### **Vector Embeddings**

* 🧩 **all-MiniLM-L6-v2** (Sentence Transformers)

### **Vector Database**

* 🗂️ **ChromaDB (Persistent Mode)**

---

## 🖥️ Recommended System Requirements

* **i5 8th Gen+ or equivalent AMD Procesor**
* **8 GB RAM**
* **4 GB Dedicated Graphics Memory**
---
## 💻 Avg Response Time 20 Seconds on My Laptop

* **i7 9750H Procesor**
* **16 GB RAM**
* **4 GB Nvidia GTX 1650 Graphics Card**
---

## 📦 Installation

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/your-username/personalized-rag-app.git
cd personalized-rag-app
```

### 2️⃣ Install Dependencies

```bash
pip install -r requirements.txt
```

### 3️⃣ Install Ollama & Pull Mistral Model

```bash
ollama pull mistral
```

---

## 📘 How It Works

### **1. Ingest PDFs**

Extract text from one or more PDF files.

### **2. Generate Embeddings**

Convert extracted text into dense vectors using the embedding model.

### **3. Store in ChromaDB**

Vectors + metadata are saved to a persistent ChromaDB directory.

### **4. Ask Questions**

Your query → converted into vector → matched with relevant context chunks.

### **5. Model Responds ONLY from Database**

Using the retrieved context, Mistral produces an accurate, grounded answer.

---

## 🎯 Use Cases

* Personalized knowledgebase chatbot
* Company internal document search
* PDF-based Q&A system
* Private AI study assistant
* FAQ generator or helpdesk automation

---

## 🤝 Contributing

Contributions are welcome!
Feel free to submit PRs, issues, or feature requests.

---

## ⭐ Give the Repository a Star!

If you like this project, help others discover it by starring ⭐ the repository.

---
