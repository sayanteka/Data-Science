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

Semantic chunker is used as text documents are splitted linewise and then those lines are combined using semantic chunker.


## Functions-Tools-Agents-with-Langchain

In lecture2: Simple chain contains prompt, model and parser. Use of runnable map in retrieval and then prompt,model
abd parser being passed. Look at interface section. It results into parsing output in json mode.

In lecture3: convert pydantic into functions(It can be multiple), bind model with functions, then create a chain where model is passes along with prompt.

In lecture 4: Same , convert pydantic into functions . It focuses on that mainly used for sentiment analysis. Doing some sort of extractions or tagging in text

In lecture5: Concept of tool. First build tools, convert to openai functions, do routing and get parsed output

In lecture 6: create conversational agent by binding tools in this way

tools = [get_current_temperature, search_wikipedia] and then converting to openai functions

https://python.langchain.com/v0.1/docs/use_cases/question_answering/conversational_retrieval_agents/

<img width="482" alt="image" src="https://github.com/user-attachments/assets/b65a4365-4b38-46ba-9977-edc7f008f3e1">

## Langgraph

Aritra sen

LangGraph_01_GettingStarted:

Start looking from Simplyfying the State addition and maintainence

Three functions are defined. 1st function does a llm call for classification. 
And then output of it goes to router based on which it
decides which one to call like either Rag or normal llm. 

llm call for classification: Router: Rag : End
   
or

llm call for classification: Router: normal llm : End

LangGraph_02_ToolCalling:

Single tool multiply is called

LangGraph_05_Bring_Human_In_the_loop_Agents:

Multiple tools are called

Lesson_2_Student:

Same thing above but from deeplearning.ai
functions are represented by nodes
And class method is defined for agent.

LLM is bind with tools.


In agent,

first llm call is made. Based on query it selects tools (1st function)

2nd function take action checks whether that tool is present. If present then it is invoked.

result displayed based on invoked.

call_openai: 1st node function

take_action: 2nd node function

exists_action: conditional function/router

Functions are represented by functions

Lesson_2_Student (1):

In this I have tried with dummy tools.

Lesson_2_Student (2):

In this agent class by combing tool and basic graph. Look at graph diagram in the code.

## Multi-modal

One multimodal solution is present in open source llms directortory by the name multi-modal-opensource. It uses chroma db to store the image embeddings. Model used is clip from hugging face. In metadata we store the path of images in local or cloud.

Once similar vectors are obtained, corresponding image in metadata fetched from user query. 

Similar thing in case of deeplearning.ai multimodal repo present in git. Only diff is weaviate library used.








