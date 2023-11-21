# Tokens 🔤

In the realm of Natural Language Processing (NLP), tokens are the basic building blocks. They are the units into which we decompose text before it can be processed by algorithms. Tokenization is the process of converting text into tokens.

## A Naive Tokenizer 🔡📏

A naive tokenizer is the most basic form of tokenization. It might involve encoding each character in the corpus as a unique number. For instance:

-   -> 1
- & -> 2
- A -> 3
- ...

This method is considered naive for several reasons:
- It results in very large vectors, especially for large texts, which is inefficient.
- Characters alone do not convey as much meaning as words or phrases.
- It doesn't capture any linguistic nuances or structure of the language.

## ChatGPT Tokenizer 🔡🤖

### Byte-Pair Encoding (BPE)

ChatGPT uses a tokenizer based on a method called Byte-Pair Encoding (BPE). This method starts with a large corpus of text and iteratively combines the most frequently adjacent pairs of characters to form new tokens. This is more efficient than the naive approach because:

- It reduces the size of the representation.
- It captures more meaning by grouping frequently occurring characters together.
- It handles rare and out-of-vocabulary words more gracefully.

## BERT Tokenizer 🔡🤖
SentencePiece

BERT employs a tokenizer that uses the SentencePiece model, which is capable of using subword units like BPE or a unigram language model. The key advantages include:

- It is language-agnostic, as it treats the text as a sequence of Unicode characters.
- SentencePiece enables the model to balance between character and word tokenizations, gaining the benefits of both.
- It efficiently handles a vast vocabulary size by breaking down words into meaningful subword units.


## Next Steps: Building Towards Embeddings

Tokenization is a critical step in transforming input text into numerical values that a neural network can understand. However, tokenization alone isn't enough. We need to turn these numbers into meaningful vectors, known as embeddings. To achieve this, we must navigate through a series of interconnected concepts:

1. **Recurrent Neural Networks (RNNs)**: these networks process sequences by maintaining a state that captures information about the elements seen so far.
2. **Long Short-Term Memory (LSTM)**: an advanced RNN that can remember long-term dependencies and forget irrelevant information.
3. **Encoder-Decoder Neural Networks**: these networks have an encoder to process the input and a decoder to generate the output, useful in tasks like translation.
4. **Attention Mechanism for Neural Networks**: this mechanism allows the network to focus on different parts of the input sequence for each step of the output sequence, much like how human attention works.
5. **Transformers**: a model architecture that eschews recurrence and instead relies entirely on attention mechanisms to draw global dependencies between input and output.

As we move forward, each concept will be built upon the previous ones, culminating in the pinnacle of Large Language Models: the Transformer architecture, which is the foundation of models like GPT and BERT.
