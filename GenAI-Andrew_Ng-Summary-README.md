## Advance RAG using Llama index:

Truelens framework for RAG evaluation.

Concept of Auto merging retrieval & sentence window retrieval.

BAAI/bge-reranker-base: Model used to rerank retrieved documents.

## Advance Retrieval

Query Translation and its validation using UMAP.

Cross encoder to rerank retrived documents.

Maximum marginal relevance.

## Fine tuning LLM

Instruction based fine tuning

Split the data, tokenization, padding and truncation.

EleutherAI/pythia-70m: Model used for fine tuning

## Chat with your data

Framework used: Langchain

Pypdf loader, youtube audio loader, whisper-parser(converting speech to text), WebBaseLoader

Recursive character splitting

Chromadb for retrieval

Retrieval: Maximum marginal relevance search is better compared to similarity search coz of diversity in context fetched for a query. Diversity in context but relevant to query.  Metadata like source=name of pdf has been added as filter while vectordb search.

Metadata is added using metadata_field_info like source as key , page as key  etc

Document compressor for efficient retrieval: 

https://colab.research.google.com/drive/1q6ejIWrorckUdkLrLsHl9PnVQhXWQ96i?usp=sharing

 LLMChainExtractor: Compresses documents retrieved from base retriever.

LLMChainExtractor, which will iterate over the initially returned documents and extract from each only the content that is relevant to the query.

At the end we will combine LLM text compressor with maximum marginal relevance search for efficient retrieval.

Q&A: chain type=map reduce or refine


