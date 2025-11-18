# YouTube-RAG — RAG with LangChain (notebook)

Simple RAG demo using a YouTube transcript, LangChain, FAISS and OpenAI embeddings / LLM.

## Files
- [rag_using_langchain.ipynb](rag_using_langchain.ipynb) — main notebook with indexing, retrieval, augmentation and generation.
- [YouTube-RAG/rag_using_langchain.ipynb](YouTube-RAG/rag_using_langchain.ipynb) — duplicate / alternate copy.

## Quickstart
1. Install dependencies (see the notebook cell):
   - youtube-transcript-api, langchain-community, langchain-openai, faiss-cpu, tiktoken, python-dotenv
2. Set your OpenAI API key in the environment (do NOT hardcode it in the notebook):
   - export OPENAI_API_KEY="sk-..."
3. Open and run the notebook: [rag_using_langchain.ipynb](rag_using_langchain.ipynb)

## Notable notebook symbols (open the notebook to see usage)
- [`splitter`](rag_using_langchain.ipynb) — RecursiveCharacterTextSplitter used for chunking.
- [`chunks`](rag_using_langchain.ipynb) — list of Document chunks from the transcript.
- [`embeddings`](rag_using_langchain.ipynb) — OpenAIEmbeddings instance.
- [`vector_store`](rag_using_langchain.ipynb) — FAISS vector store built from chunks.
- [`retriever`](rag_using_langchain.ipynb) — retriever from the vector store.
- [`prompt`](rag_using_langchain.ipynb) — PromptTemplate for LLM queries.
- [`context_text`](rag_using_langchain.ipynb) and [`final_prompt`](rag_using_langchain.ipynb) — prepared context & prompt.
- [`llm`](rag_using_langchain.ipynb) and [`answer`](rag_using_langchain.ipynb) — ChatOpenAI instance and generated answer.
- [`format_docs`](rag_using_langchain.ipynb) — helper to format retrieved docs.
- [`parallel_chain`](rag_using_langchain.ipynb) and [`main_chain`](rag_using_langchain.ipynb) — runnable chain composition.

## Usage tips
- Replace the embedded or example API key with a secure env var.
- Tune chunk_size / chunk_overlap in [`splitter`](rag_using_langchain.ipynb) for longer/shorter transcripts.
- Persist the FAISS index if you plan repeated queries (see vector_store creation in the notebook).

