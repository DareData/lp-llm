## LlamaIndex 🦙

### Connecting Custom Data and Large Language Models

LlamaIndex can be considered as the main tool that bridges text data and LLMs, making data more accesible for creating custom applications and workflows. It streamlines the processes of data ingestion, structuring, retrieval, and integration with various application frameworks.

The firs step is to understand the two key components of LlamaIndex: **Data Connectors** and **Data Indexes**.
Then, we need to learn how to **build a Knowledge Base with LlamaIndex**.
And, finally, explore some of the different **advanced customization options** and **methods** in this framework.

This four aspects are the key points for this section and will give you a clear explanation of the core functionalities and practical applications of LlamaIndex.


### DATA CONNECTORS

Data Connectors in LlamaIndex fetch and ingest data from various sources such as APIs, databases and file formats (PDFs, JSON, etc). These are essential as they represent the entry point for any data that enter into your system and will be later processed (indexed and queried).

Some common use cases are data ingestion from Notion, Slack, Google Docs, etc. The connectors ensure that your data is easily brought into the system, ready for indexing.


### DATA INDEXES

After ingestion, data needs to be organized. Data Indexes in LlamaIndex help to structure the ingested data into manageable units called Documents or Nodes. These indexes allow you to create connections between chunks of data, enabling an easier retrieval and integration with VectorStore providers.

The ability to link this small segments of a larger dataset (chunks) in a sequence, such as indicating the previous and next pieces of text, enhances the data's relational structure.


### BUILDING A KNOWLEDGE BASE WITH LLAMAINDEX

LlamaIndex simplifies the process of creating a knowledge base by standardizing procedures and adding extra structure to your data. This process can be divided into two main stages: Indexing and Queriying.

The two main reasons to use this tool in this type of procedures are: 
- it eases and standarizes the whole procedure, allowing integrations from different types of sources and migrations (changing from a database provider into a new one, for example).
- it adds extra structure/information to the database.

**Indexing Stage**:

Is where you prepare your knowledge base by using Data Connectors to ingest data, that is then organized into Documents or Nodes (the base unit of information for LlamaIndex).

**Querying Stage**:

involves fetching relevant information from your knowledge base in response to queries. The querying process in LlamaIndex is customizable and involves three main steps:

- Retrieval: Find and return the most relevant documents.
- Postprocessing: Rerank, transform, or filter retrieved Nodes, applying metadata like keywords to enhance relevance.
- Response Synthesis: Combine the query, relevant data, and the prompt. And then send them to the LLM to generate a response.

This Querying process is highly customizable and there are many methods and techniques to carry out these actions.
In the [Llama-Methods](01.1-llama-methods.md) file we'll show some methods to implement this advanced customization.

#### EXAMPLE

In the following Notebook you will find a practical example of the concepts discussed in this section. This simple example demonstrates how to ingest data, create an index and perform a query.

[First Example Notebook](first_example.ipynb)
