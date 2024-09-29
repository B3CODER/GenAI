# PDF Search Application Using ChromaDB and Generative AI

## Overview
This project is a Generative AI-powered Question Answering (QA) system that enables users to search their PDF documents. It uses ChromaDB to store document embeddings, Hugging Face’s LaMini-T5-738M model for text generation, and LangChain for chaining together language models and vector databases.

## Key Features:
Upload PDF files and split them into smaller chunks using RecursiveCharacterTextSplitter.
Store document chunks in ChromaDB, a vector database, using embeddings.
Use Hugging Face's LaMini-T5-738M model for generating answers based on user queries.
Retrieve relevant chunks from ChromaDB using LangChain and answer user queries.
