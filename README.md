# RAG-Powered Resume Q&A Assistant 🤖
This project implements a complete Retrieval-Augmented Generation (RAG) pipeline to enable intelligent, domain-specific question-answering over unstructured PDF documents, specifically resumes. It serves as a proof-of-concept for the EXPT 8 – Retrieval Augmented Generation (RAG) Based Gen-AI Tool requirement. The core utility is to quickly extract and synthesize specific information (e.g., work experience, projects, or skills) from a private knowledge base, thereby reducing LLM hallucination and ensuring responses are factual and grounded.
# Project Objectives & Features
The RAG pipeline successfully meets these core requirements:RAG Core Implementation: Designs and implements an end-to-end RAG pipeline, covering Ingestion (PDF $\rightarrow$ Chunks $\rightarrow$ Vectors) and Inference (Query $\rightarrow$ Retrieve $\rightarrow$ Generate).Vector Database Utilization: Uses FAISS (IndexFlatL2) for highly efficient vector indexing and similarity search.Domain-Specific Q&A: The application intelligently answers queries over the uploaded PDF (e.g., a resume).Anti-Hallucination: A robust prompt template enforces the LLM to use only the retrieved context, minimizing fabricated answers.
# ⚙️ Technical Stack
That's clear! I'll provide the complete, detailed README.md in a clean, point-based format without any tables.🤖 RAG-Powered Document Q&A Assistant (EXPT 8)This project implements a complete Retrieval-Augmented Generation (RAG) pipeline to enable intelligent, domain-specific question-answering over unstructured PDF documents, specifically resumes. It serves as a proof-of-concept for the EXPT 8 – Retrieval Augmented Generation (RAG) Based Gen-AI Tool requirement.The core utility is to quickly extract and synthesize specific information (e.g., work experience, projects, or skills) from a private knowledge base, thereby reducing LLM hallucination and ensuring responses are factual and grounded.🌟 Project Objectives & FeaturesThe RAG pipeline successfully meets these core requirements:RAG Core Implementation: Designs and implements an end-to-end RAG pipeline, covering Ingestion (PDF $\rightarrow$ Chunks $\rightarrow$ Vectors) and Inference (Query $\rightarrow$ Retrieve $\rightarrow$ Generate).Vector Database Utilization: Uses FAISS (IndexFlatL2) for highly efficient vector indexing and similarity search.Domain-Specific Q&A: The application intelligently answers queries over the uploaded PDF (e.g., a resume).Anti-Hallucination: A robust prompt template enforces the LLM to use only the retrieved context, minimizing fabricated answers.⚙️ Technical StackThis project is built using the following key technologies:Language: Python 3.10+Document Loading: pypdf is used to extract raw text from the input PDF file.Text Splitter: langchain.text_splitter.RecursiveCharacterTextSplitter is employed to split the raw text into semantically coherent, manageable, overlapping chunks (512 tokens with 50 overlap).Embedding Model: SentenceTransformer (all-MiniLM-L6-v2) converts text chunks and the user query into high-dimensional numerical vectors.Vector Store: FAISS (faiss-cpu) stores the chunk vectors and performs fast similarity search.Generative LLM: TinyLlama/TinyLlama-1.1B-Chat-v1.0 synthesizes the final human-readable answer based on the retrieved facts.

# 🧠 Theoretical Workflow of RAG
The RAG pipeline operates in two phases:
1) Ingestion/Indexing: Documents are converted into numerical representations called vector embeddings. These vectors are stored and indexed in the FAISS vector database for efficient search.
2) Query & Generation:
The user's question is also converted into a vector.
A similarity search retrieves the most relevant document chunks (context) from the FAISS index.
This context is injected into the prompt and sent to the LLM (TinyLlama), which synthesizes a grounded answer.

# 🎯 Real-Life Use Cases
The RAG pattern is critical for applications demanding factual accuracy and access to private or time-sensitive data:
Enterprise Knowledge Management 🏢: Querying private company manuals, HR policies, or internal research reports.
Customer Service and Support 📞: Powering chatbots with up-to-date product specifications and service FAQs.
Financial and Legal Compliance ⚖️: Generating responses based on specific regulatory documents, ensuring all facts are verifiable.
Real-Time Financial Signal Notifier 💰: Analyzing real-time news sentiment and technical data (like RSI or Moving Average crossovers) to issue grounded Bullish or Bearish trading alerts.
# 💬 Usage Examples
Query: "What is the work experience mentioned in the resume?"
Query: "Can you list all the key projects and their technologies?"
Query: "What programming languages does the candidate know?"
