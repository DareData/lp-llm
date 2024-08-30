## ADVANCED CUSTOMIZATION OPTIONS - METHODS

To maximize the effectiveness of LlamaIndex in your applications, you can use many advanced customization options. These methods allow you to adjust how data is retrieved, processed, and synthesized; providing greater control and precision in your interactions with LLMs.

LlamaIndex stands out not only for its wide range of this built-in methods, but also for its flexibility. You can create and personalize your own methods adjusted to the specific needs and dependencies of your project. This adaptability makes LlamaIndex a powerful tool for building customized, efficient, and scalable LLM applications.

This section provides an overview of some interesting techniques that you can use.

### 1. Custom Token Parsing (with **SentenceWindowParser**):

Enables parsing and segmenting long documents into manageable chunks based on sentence boundaries. This is useful for processing large texts where maintaining context over long distances can be challenging. By splitting text into smaller windows (that contain a fixed number of sentences), you can ensure that the context remains coherent during retrieval and processing.

Example: A piece of code illustrating a SentenceWindowParser implementation. 

> Note that the code is not complete; we just show the important and relevant parts in this technique. You'll have to integrate these pieces of code into the full LLM implementation.

```python
# Creating the sentence window node parser w/ default settings
node_parser = SentenceWindowNodeParser.from_defaults(
    window_size=3,
    window_metadata_key="window",
    original_text_metadata_key="original_text",
)
# Extracting out the set of nodes that will be stored in the VectorIndex
nodes = node_parser.get_nodes_from_documents(documents)
# Building the sentence index
sentence_index = VectorStoreIndex(nodes)
# Using the MetadataReplacementPostProcessor to replace the sentence in each node with it's surrounding context
query_engine = sentence_index.as_query_engine(
    similarity_top_k=2,
    # the target key defaults to `window` to match the node_parser's default
    node_postprocessors=[
        MetadataReplacementPostProcessor(target_metadata_key="window")
    ],
)
window_response = query_engine.query(
    "-- your question here"
)
print(window_response)
```


### 2. Custom Retrieval Configurations (using **Retriever with Metadata filter**):

Allows adjusting how documents are retrieved from an index based on specific criteria. By using a metadata filter with a retriever, you can focus on retrieving only those documents that match certain metadata conditions (e.g., author, date, type). This helps to improve the relevance of the results returned by your queries, ensuring that only the most relevant data is fetched and improving the efficiency and accuracy of your LLM interactions.


### 3. Advanced Postprocessing Nodes (with **QueryBundle**):

Permits refining the results of a query by processing nodes in a way that considers additional query hints. The postprocessor do it by "taking" a set of nodes and applying transformations or filters before returning them. The QueryBundle technique lets you bundle multiple queries or additional context together to improve the accuracy and relevance of the retrieved nodes.


### 4. Flare:

Flare is a method designed to enhance the retrieval process by providing a more dynamic and context-aware interaction with the data. It adapts to the user's query by focusing on the most relevant portions of the document and offering refined suggestions, leading to more accurate and contextually appropriate responses. This whole process helps to reduce hallucinations.

Example: A piece of code illustrating a Flare implementation.
```python
from llama_index.core.query_engine import FLAREInstructQueryEngine

flare_query_engine = FLAREInstructQueryEngine(
    query_engine=index_query_engine,
    max_iterations=7,
    verbose=True,
)
response = flare_query_engine.query(
    "-- your question here"
)
```

## 5. Raptor:

Raptor is another advanced technique in LlamaIndex designed for building solid RAG applications in production. This model is based on constructing a tree structure that encapsulates both granular details and overarching narratives. Raptor applies optimized algorithms to integrate information across extensive documents at varying abstraction levels, significantly enhancing question-answering tasks, particularly those requiring multi-step reasoning.

In the following link you have a Notebook example of this technique:

[RAPTOR example (github)](https://github.com/run-llama/llama_index/blob/main/llama-index-packs/llama-index-packs-raptor/examples/raptor.ipynb)

_____

We covered these five techniques to give you an overview of advanced customization methods. But remember you can always explore more modules
and features in the [llamaindex.ai](https://llamaindex.ai/) documentation. 
