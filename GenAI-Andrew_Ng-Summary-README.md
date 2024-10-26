## Advance RAG using Llama index:

Truelens framework for RAG evaluation.

Concept of Auto merging retrieval & sentence window retrieval.

BAAI/bge-reranker-base: Model used to rerank retrieved documents.

## Advance Retrieval

Query Translation and its validation using UMAP.

Cross encoder to rerank retrived documents.

Maximum marginal relevance.

## Udemy_OpenAI_Machine-Learning-Data-Science-and-Generative-AI-with-Python


## Fine tuning LLM

Instruction based fine tuning. Look it from data_prep.ipynb

Data should be in table with one column as Question and another column as Answer.

Data conversion to required form and then perform tokenization, padding and truncation.

Max steps to train for (max_steps=max_steps): If batch size=5. It means in each batch 5 samples will be used for
training. For how long? Steps come into the picture i.e for 3 times if max_steps=3 and so on.

overwrite_output_dir=False: Prevents overwriting the contents of the output directory if it already exists.

eval_steps=120: Evaluates the model every 120 steps (batches) to assess its performance on a validation set.

save_steps=120: Saves the model's checkpoints every 120 steps.

The target learning rate is the final learning rate that the optimizer will reach after the warmup period .

Role of warmup-steps: If the initial learning rate is 1e-5, the target learning rate is 1e-3, and the warmup steps are 1000, then the learning rate will increase by 9e-7 per step for the first 1000 steps.

Parameter for training can be checked from summarization model in github

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

LLMChainExtractor, which will iterate over the initially returned documents and extract from each only the content that is relevant to the query: In retrieval.ipynb

At the end we will combine LLM text compressor with maximum marginal relevance search for efficient retrieval.

Q&A: chain type=map reduce or refine

ConversationalRetrievalChain : In chat.ipynb


## Udemy_OpenAI_Machine-Learning-Data-Science-and-Generative-AI-with-Python 

Data agent.ipynb talks about use of agentic RAG . Like there can be diff retrievers as tools. Fed to llm and then based on description each retriever is selected.

Data_Advance_Rag talks about query rewriting, document compression 
<img width="587" alt="image" src="https://github.com/user-attachments/assets/eeed523b-40fa-46fd-87a9-a655d49dc240">





