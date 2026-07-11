# 📄 LangChain Document Loaders

This repository contains examples of using **LangChain Document Loaders** to load data from different sources into LangChain `Document` objects. These loaders are commonly used as the first step in Retrieval-Augmented Generation (RAG) pipelines before text splitting, embedding generation, and vector storage. :contentReference[oaicite:0]{index=0}

---

## 🚀 Features

- Load text files
- Load PDF documents
- Load CSV files
- Load web pages
- Load entire directories
- Work with LangChain `Document` objects
- Ready for RAG applications

---

## 📁 Project Structure

```text
Document-Loaders/
│
├── text_loader.py
├── pdf_loader.py
├── csv_loader.py
├── web_loader.py
├── directory_loader.py
├── sample_data/
│   ├── sample.txt
│   ├── sample.pdf
│   └── sample.csv
│
├── requirements.txt
└── README.md
```

---

## 📦 Installation

Clone the repository

```bash
git clone https://github.com/yourusername/document-loaders.git
cd document-loaders
```

Install dependencies

```bash
pip install -r requirements.txt
```

---

## 📚 Required Packages

```bash
pip install langchain
pip install langchain-community
pip install pypdf
pip install beautifulsoup4
pip install unstructured
pip install python-dotenv
```

---

# 📄 Text Loader

```python
from langchain_community.document_loaders import TextLoader

loader = TextLoader("sample.txt")

docs = loader.load()

print(docs[0].page_content)
```

---

# 📄 PDF Loader

```python
from langchain_community.document_loaders import PyPDFLoader

loader = PyPDFLoader("sample.pdf")

docs = loader.load()

print(docs[0].page_content)
```

---

# 🌐 Web Loader

```python
from langchain_community.document_loaders import WebBaseLoader

loader = WebBaseLoader(
    "https://python.langchain.com"
)

docs = loader.load()

print(docs[0].page_content)
```

---

# 📊 CSV Loader

```python
from langchain_community.document_loaders import CSVLoader

loader = CSVLoader("sample.csv")

docs = loader.load()

print(docs[0].page_content)
```

---

# 📂 Directory Loader

```python
from langchain_community.document_loaders import DirectoryLoader

loader = DirectoryLoader(
    "sample_data",
    glob="**/*.txt"
)

docs = loader.load()

print(len(docs))
```

---

## 📑 Document Object

Every loader returns a list of `Document` objects.

Example:

```python
Document(
    page_content="Hello World",
    metadata={
        "source": "sample.txt"
    }
)
```

---

## ⚡ Common Methods

| Method | Description |
|---------|-------------|
| `load()` | Loads all documents into memory |
| `lazy_load()` | Streams documents one at a time for large datasets |

---

## 🧠 Where Document Loaders Fit in RAG

```
Documents
      │
      ▼
Document Loader
      │
      ▼
Text Splitter
      │
      ▼
Embeddings
      │
      ▼
Vector Store
      │
      ▼
Retriever
      │
      ▼
LLM
```

---

## 📖 Supported Data Sources

LangChain supports document loaders for many sources, including:

- Text files
- PDFs
- CSV
- JSON
- HTML
- Microsoft Word
- PowerPoint
- Google Drive
- Notion
- Slack
- GitHub
- Confluence
- YouTube Transcripts
- Wikipedia
- Web URLs
- Amazon S3
- Dropbox
- OneDrive
- SharePoint

…and many more. :contentReference[oaicite:1]{index=1}

---

## 📚 Learn More

Official LangChain documentation:

- https://docs.langchain.com/oss/python/integrations/document_loaders

---

## ⭐ Author

**Parika Chaudhary**

B.Tech CSE (AI & DS)

Machine Learning | Generative AI | LangChain | RAG | LLMs
