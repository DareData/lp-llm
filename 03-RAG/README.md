# Retrieval-Augmented Generation

Retrieval-Augmented Generation (RAG) is an approach that optimizes the performance of a Large Language Model (LLM) by retrieving relevant information from a knowledge base, outside of its training data, before generating a response. This process ensures that the generated output is grounded in specific, up-to-date, and reliable information. 

As we know, LLMs are trained on large amounts of data and many parameters to generate original results for different tasks such as question answering or translation. RAG extends these powerful capabilities by allowing LLMs to access specific domains or an organization’s internal knowledge base — all without needing to retrain the model.

Many applications use this approach because it is easy to implement, just involving stting up the architecture and sending requests to popular providers.
RAG extends the capabilities of standard LLMs by allowing the models to access specific domains or an organization’s internal knowledge base without needing to retrain the model.

This module is then divided as follows:

- [RAG](01-RAG.md): an explanation on why RAG is needed and what the main ideas are
- [Implementation](02-implementation.md): explaining the implementation of basic RAG structures in some different ways.
- [Applications](02-applications.md): the most subtle thing regarding RAG is how to build the solutions using this technique. For that reason, we have a section discussing possible use-cases for RAG and some further sophistications regarding each use-case.
