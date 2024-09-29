# PDF Search Application Using ChromaDB and Generative AI

## Overview
This project is a Generative AI-powered Question Answering (QA) system that enables users to search their PDF documents. It uses ChromaDB to store document embeddings, Hugging Face’s LaMini-T5-738M model for text generation, and LangChain for chaining together language models and vector databases.

## Key Features:
Upload PDF files and split them into smaller chunks using RecursiveCharacterTextSplitter.
Store document chunks in ChromaDB, a vector database, using embeddings.
Use Hugging Face's LaMini-T5-738M model for generating answers based on user queries.
Retrieve relevant chunks from ChromaDB using LangChain and answer user queries.

# Workflow Overview
PDF Parsing and Text Splitting:
The system loads PDF files from a directory using PDFMinerLoader.
Text from the PDFs is split into smaller chunks using RecursiveCharacterTextSplitter, ensuring efficient processing.
Embedding Generation and Storage in ChromaDB:

Embeddings are generated using SentenceTransformerEmbeddings from the langchain_community library.
These embeddings are stored in ChromaDB, enabling efficient document search and retrieval.
Question Answering Pipeline:

The LaMini-T5-738M model from Hugging Face is utilized for generating answers to user queries.
RetrievalQA from LangChain is used to retrieve relevant document chunks from ChromaDB, which are then processed by the language model to generate accurate answers.
Streamlit UI:

The user interface is built using Streamlit, allowing users to input questions and receive generated answers based on the PDF content.
