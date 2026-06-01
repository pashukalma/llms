### Space Exploration RAG Pipeline: Dataset Creation & Vector Storage

This Notebook implements the foundational stages of a RAG pipeline. The project focuses on scraping space exploration data from Wikipedia, processing and chunking the text, generating vector embeddings, and storing them in a specialized vector database.

#### Features

*   **Automated Web Scraping:** Pulls comprehensive text data from 20 targeted Wikipedia articles related to space programs, telescopes, and astronautics.
*   **Data Sanitization:** Cleans raw HTML content by removing Wikipedia reference brackets (e.g., `[1]`), bibliographies, and external link sections.
*   **Text Chunking:** Efficiently splits long-form articles into manageable, fixed-size text segments suited for LLM context windows.
*   **Vector Embeddings:** Generates semantic vectors using OpenAI's `text-embedding-ada-002` model.
*   **Vector Store Integration:** Stores raw text chunks alongside their corresponding embeddings in a local DeepLake dataset.


### Architecture Overview

#### Pipeline Component #1: Data Collection & Preparation
1. **Scraping:** Uses `requests` and `BeautifulSoup` to target 20 distinct Wikipedia endpoints (e.g., Apollo Program, SpaceX, ISS).
2. **Cleaning:** Decomposes non-narrative elements and extracts clean, raw text.
3. **Chunking:** Segments text into consistent `chunk_size = 1000` character intervals.

#### Pipeline Component #2: Storage & Retrieval Vectorization
1. **Initialization:** Creates a DeepLake dataset scheme with explicit column types (`Text` and `Embedding`).
2. **Embedding Generation:** Passes text arrays through OpenAI's embedding API.
3. **Commit:** Appends and commits the vectorized indices to a local `/content/inverted_index` directory.