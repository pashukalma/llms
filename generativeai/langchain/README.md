### LangChain Exploration & Reference Guide

This repository contains a comprehensive Jupyter Notebook (`langchain_various.ipynb`) exploring the core mechanics, components, and practical implementations of the LangChain framework in Python. It acts as a modular reference guide for building LLM-powered applications, advanced RAG (Retrieval-Augmented Generation) pipelines, and autonomous agent frameworks.

#### 📌 Core Architecture Covered
1. **Application Foundations**: Contrast between traditional software architectures and modern, token-driven LLM applications (Client ➔ Prompt ➔ LLM ➔ Parser output).
2. **Memory & Statefulness**: Implementations of `ConversationBufferMemory`, `ConversationBufferWindowMemory`, `ConversationKGMemory`, and `ConversationEntityMemory`.
3. **LCEL & Chains**: Structuring workflows using LangChain Expression Language (LCEL) and classic legacy `LLMChain` interfaces.
4. **Multi-Model Integrations**: Hands-on configurations with OpenAI, Google GenAI (Gemini), Hugging Face Pipelines, and local instances via GPT4All.
5. **Advanced Retrieval (RAG)**:
   - Distance calculation and geometric validation via `scipy.spatial`.
   - Vector libraries and databases (Faiss, Chroma, DocArray, Pinecone, Qdrant).
   - Specialized retrieval pipelines featuring `KNNRetriever` and `PubMedRetriever`.
   
6. **Agentic Frameworks**: Implementation of ReAct agents using `create_react_agent` along 
with execution strategies like Zero-shot ReAct and Plan-and-Solve.

#### 🛠️ Complete Project: Chat-with-Your-Documents
The notebook includes a production-ready, interactive Streamlit full-stack app demonstrating document loading, custom chunk extensions, and RAG execution:
- **Loaders**: Supports `.pdf`, `.txt`, `.docx`, and custom `.epub` element extraction.
- **Transform**: Chunks files via `RecursiveCharacterTextSplitter`.
- **Vector Storage**: Employs Hugging Face `all-MiniLM-L6-v2` embeddings stored locally within a `DocArrayInMemorySearch` database.
- **Retrieval Engine**: Performs Maximum Marginal Relevance (`mmr`) filtering to ensure diverse context fetching.
- **Interface**: Implements a chat interface via Streamlit using a streaming `ConversationalRetrievalChain`.


