# RAG-based Question Answering System

This project is a simple implementation of a **Retrieval-Augmented Generation (RAG)** system for question answering. It's designed to answer questions by first retrieving relevant documents from a knowledge base and then using a generative language model to synthesize an answer based on the retrieved information.

This system was built for a college lab to demonstrate the core principles of the RAG architecture.

***

## 🏛️ How It Works: The RAG Pipeline

The system follows a two-stage process to answer a user's query:

1.  **Retrieval Stage:** When a user asks a question, the system first searches through a database of documents to find the ones that are most likely to contain the answer. This project uses the **BM25 algorithm**, a classical keyword-based search method, to score and rank documents based on their relevance to the query.

2.  **Generation Stage:** The top-ranked documents from the retrieval stage are combined to form a **context**. This context, along with the original question, is then fed into a sequence-to-sequence language model. The model, in this case, is Facebook's **BART (BART-large-cnn)**, which generates a human-like answer based *only* on the provided context.



This approach allows the language model to access external knowledge, reducing hallucinations and providing more factual, up-to-date answers compared to a standard language model alone.

***

## 🛠️ Technologies & Models Used

* **Dataset:** `wikipedia` ('20220301.simple' version) from the Hugging Face `datasets` library.
* **Retriever:** `rank_bm25` for efficient BM25 sparse retrieval.
* **Generator:** `facebook/bart-large-cnn` from the Hugging Face `transformers` library.
* **Embeddings (for future enhancement):** `sentence-transformers/all-mpnet-base-v2` is included but not used in the final retrieval logic.
* **Core Libraries:** `PyTorch`, `NumPy`, `transformers`, `sentence-transformers`, `datasets`.

***

## 🚀 Getting Started

Follow these steps to set up and run the project on your local machine.

### 1. Clone the Repository

```bash
git clone <your-repository-url>
cd <repository-directory>
