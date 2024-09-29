# PDF Search Application Using ChromaDB and Generative AI

## Overview

This project is a **Generative AI-powered Question Answering (QA) system** that enables users to search their PDF documents. It uses **ChromaDB** to store document embeddings, Hugging Face's **LaMini-T5-738M** model for text generation, and **LangChain** for chaining together language models and vector databases.

### Key Features:

* Upload PDF files and split them into smaller chunks using **RecursiveCharacterTextSplitter**.
* Store document chunks in **ChromaDB**, a vector database, using embeddings.
* Use Hugging Face's **LaMini-T5-738M** model for generating answers based on user queries.
* Retrieve relevant chunks from ChromaDB using **LangChain** and answer user queries.

## Workflow Overview

1. **PDF Parsing and Text Splitting:**
   * The system loads PDF files from a directory using `PDFMinerLoader`.
   * Text from the PDFs is split into smaller chunks using `RecursiveCharacterTextSplitter`, ensuring efficient processing.

2. **Embedding Generation and Storage in ChromaDB:**
   * Embeddings are generated using **SentenceTransformerEmbeddings** from the `langchain_community` library.
   * These embeddings are stored in **ChromaDB**, enabling efficient document search and retrieval.

3. **Question Answering Pipeline:**
   * The **LaMini-T5-738M** model from Hugging Face is utilized for generating answers to user queries.
   * **RetrievalQA** from LangChain is used to retrieve relevant document chunks from ChromaDB, which are then processed by the language model to generate accurate answers.

4. **Streamlit UI:**
   * The user interface is built using **Streamlit**, allowing users to input questions and receive generated answers based on the PDF content.

## Components

### Hugging Face Model - LaMini-T5-738M

**LaMini-T5-738M** is a lightweight text-to-text model from MBZUAI's LaMini family. It is designed for efficient question answering tasks. The model generates answers by understanding the context of questions based on provided document content. You can download the model via Hugging Face's repository:

```bash
git lfs install
git clone https://huggingface.co/MBZUAI/LaMini-T5-738M
```

### LangChain_Community Library

The `langchain_community` library provides connectors and tools to integrate various models, embeddings, and databases into an AI system. Here are some key modules used in the project:

* **PDFMinerLoader**: Loads text from PDF documents.
* **SentenceTransformerEmbeddings**: Converts text into numerical vectors (embeddings).
* **Chroma**: A vector store to store and retrieve document embeddings.
* **HuggingFacePipeline**: Integrates Hugging Face's pre-trained models into the LangChain ecosystem.
* **RetrievalQA**: A QA chain that retrieves relevant documents from Chroma and generates answers using the language model.

### ChromaDB

**ChromaDB** is a high-performance vector database designed for handling embeddings. It supports fast, scalable storage and retrieval of text embeddings, enabling efficient search and question-answering across large document sets. By persisting data in `duckdb+parquet`, it ensures low-latency access while maintaining durability.
### ChromaDB Architecture
![ChromaDB](https://github.com/user-attachments/assets/33a4648b-ddfb-4f12-a0c9-e33774051992)


## Setup Instructions

1. Clone the Repository

```bash
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name
```

2. Install Dependencies

```bash
pip install -r requirements.txt
```

3. Download Hugging Face Model

```bash
git clone https://huggingface.co/MBZUAI/LaMini-T5-738M
```

4. Run the Streamlit Application

```bash
streamlit run app.py
```

## Conclusion

This project demonstrates how to use **ChromaDB**, **LangChain**, and **Hugging Face** models to build an effective PDF search and question-answering tool. By combining text embeddings and generative models, users can search large volumes of text data and get relevant answers efficiently.

