# Retrieval-Augmented Generation

The most limiting factor of LLM models is that they have only had access to their training data. Althought there are some ways of circumventing this issue like fine-tuning, which we will discuss in the next section. However, one of the most common and cheaper options is Retrieval-Augmented Generation or RAG.

It solves a couple of issues, but the most common ones are:
1. __Outdated training data__: some applications may require access to the latest information like the weather, some transactions, etc.
2. __No references for the answer__: we know that LLM's have the tendency to hallucinate, so knowing where the reply came from, its source, is fundamental to pinpoint these cases.


RAG is a very simple technique to understand: it consists on creating an augmented answer based on retrieved information. And how does this work? Now that you are familiar with indexation and ingestion, you know that we have ways of associating an entity that is LLM-based in nature, the embeddding, to chunks of text that constitute our sources.  

The most basic RAG is therefore based on comparing a query (a question or some request) to the most similar chunks of text. This way, we can retrieve the most relevant information from our knowledge base and provide it to the model in order to reply to said query. 

<img src="../images/Jq9bEbitg1Pv4oASwEQwJg.png" alt="" width="3000" height="auto">

> Note: we will see in a following section that we can give LLM models the ability to use tools to retrieve extra information.

