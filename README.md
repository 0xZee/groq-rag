# RAG Application with Langchain, Chroma, and Groq Llama3

This repository contains an example of a Retrieval Augmented Generation (RAG) application built using Langchain, Chroma, and Groq Llama3. The RAG system combines retrieval-based methods with language models to generate coherent and contextually relevant responses.

## Components

1. **Langchain**:
   - Langchain provides the core functionality for handling language models, prompts, and text processing.
   - We use the Llama3 LLM (Large Language Model) from Langchain for text generation.

2. **Chroma**:
   - Chroma is used as the vector store for document embeddings.
   - It organizes and indexes documents based on high-dimensional vectors.

3. **Groq Llama3**:
   - Groq Llama3 is integrated for querying and retrieving relevant documents.
   - It combines Groq queries with Llama3 embeddings to fetch contextually relevant information.

4. **Community Document Loaders**:
   - We use WebBaseLoader and PyPDFLoader to load documents from web pages and PDF files.
   - These loaders allow us to retrieve diverse content for the RAG system.

5. **Text Splitters**:
   - RecursiveCharacterTextSplitter is employed to chunk and preprocess text data.
   - It ensures that documents are appropriately split for indexing and retrieval.

6. **Output Parsers and Runnables**:
   - StrOutputParser handles the output formatting for user-friendly responses.
   - RunnablePassthrough allows seamless integration of different components.

## Usage

1. **Installation**:
   - Install the required Python packages using `pip install langchain chroma groq-llama3`.

2. **Configuration**:
   - Set up your Cohere API key and other necessary credentials.
   - Configure ChromaDB connection details.

3. **Create Retrieval Chain**:
   - Use `create_retrieval_chain` to create a retrieval pipeline.
   - Combine Groq Llama3 queries with ChromaDB retrieval.

4. **Combine Documents**:
   - Use `create_stuff_documents_chain` to combine and preprocess documents.
   - Apply text splitters and other relevant processing steps.

5. **Run the RAG System**:
   - Initialize the RAG system with Langchain, Chroma, and Groq Llama3.
   - Provide user prompts and retrieve contextually relevant information.

## Example
```python
from langchain_cohere import CohereEmbeddings, ChatCohere
from langchain_core.prompts import ChatPromptTemplate
from langchain_groq import ChatGroq
from google.colab import userdata

# Initialize components (replace with actual configurations)
cohere_api_key = 'your-cohere-api-key'
chroma_connection_string = 'your-chroma-db-connection-string'

# Create your RAG system using Langchain, Chroma, and Groq Llama3
# ...

# Example usage
question = "What is the capital of France?"
documents = ["Paris is the capital of France.", "Berlin is the capital of Germany."]
response = rag.ask(question, documents)
print(response)
