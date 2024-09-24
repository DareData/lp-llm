# The building blocks of Large Language Models: Transformers ⚙️

How can we do seq2seq tasks, while maintaining the meaning nuances of the context of the sentence?

The answer: **Transformers**

Transformers is the pinacle structure when creating Large Language models. At its core, the vanilla transformer model consists of two primary components:

- **Encoders**: processes the input sequence and create a set of representations that capture the nuances of the input data
- **Decoders**: takes these representations and generates an output sequence.

## Encoder Structure 📈🔍

The encoder of a transformer model is designed to parse the input sequence and convert it into a higher-dimensional space where relationships between the data points can be more easily discerned. It is typically composed of a stack of identical layers, each containing two main sub-layers:

- **Embedding Layer**
- **Positional Encoding Layer**
- **Self-Attention Layer**

The embedding layer converts the input tokens into numerical vectors, while the positional encoding layer provides information about the position of the tokens in the sequence. The self-attention layer allows the model to focus on different parts of the input sequence when encoding the data.

## Decoder Structure 📉🔎

The decoder in a transformer model mirrors the encoder with additional components specific to its role in generating the output sequence. It also consists of a stack of identical layers, but each unit has an additional sub-layer: **Encoder-Decoder Attention** that helps the decoder focus on appropriate segments of the input sequence.

The self-attention mechanism within the decoder allows each position in the decoder to attend to all positions in the decoder up to and including that position. Attention masks ensure that the predictions for a given position can depend only on the known outputs at positions before it, preserving the auto-regressive property.

## Layers

### Embeddings 📚🔢

Since you already know that Neural Networks only work with numbers, it is easy to understand that the first piece of the puzzle is **Word Embedding**. They are present in both Encoder and Decoder units, and their output should be a numerical representation of words, phrases, or sentences that capture their meaning and context in a high-dimensional space.

### Positional Encoding 🌐📍

Positional encoding is a technique used to give the model information about the relative or absolute position of the tokens in the sequence.

The original transformer paper proposed using sine and cosine functions of different frequencies to encode the positions. These functions provide a unique position signal to each token which can be scaled and manipulated along with the token embeddings through the layers of the transformer, thus preserving the order information.

### Self-Attention Mechanism 👀💡

An essential feature of transformers is the use of **attention mechanisms**, which allow the model to focus on different parts of the input sequence when producing the output, akin to how a human pays more attention to specific words while reading a sentence. This mechanism is pivotal in handling long-range dependencies in the data.

Imagine you're reading a book and trying to understand the meaning of a particular word in a sentence. To do this effectively, you need to consider not just the word itself but also its context – the words around it. This is essentially what the self-attention mechanism does in a transformer model.

### The Concept

**Self-attention** allows a transformer model to consider the entire input sequence (the whole sentence, for instance) simultaneously. It determines the relevance or "attention" that each part of the input should receive when forming a representation of a specific word. This means that when the model is trying to understand one word, it looks at other words in the sentence to see which ones are important in giving the word its meaning.

### How It Works: Metaphor

Think of the self-attention mechanism as a team of detectives working together to solve a case. Each detective (representing a word in the sentence) needs to figure out how much attention they should pay to other detectives (other words) to solve the case (understand the meaning of the sentence).

1. **Query Vector (Q):** This is like a detective asking questions about their specific part of the case.
2. **Key Vector (K):** This is like each detective sharing important pieces of evidence they have.
3. **Value Vector (V):** This represents the actual information each detective brings to the table.

### The Process

1. **Creating Vectors:**
   - For each word (detective) in the sentence, the model creates three vectors: a query vector, a key vector, and a value vector.

2. **Calculating Attention Scores:**
   - The model computes an "attention score" by taking the dot product (a mathematical operation) of the query vector of one word with the key vectors of all words in the sentence. This score tells us how much attention each word should pay to other words.
   - Imagine a detective asking all other detectives questions and then evaluating the relevance of each answer to their query.

3. **Softmax Operation:**
   - After calculating the scores, the model applies a softmax function to these scores. This converts them into probabilities (weights) that sum to one. It’s like prioritizing which pieces of evidence are the most crucial to focus on.

4. **Weighted Sum:**
   - Finally, the model uses these weights to compute a weighted sum of the value vectors. This means that each word's representation is adjusted by considering how much attention it should pay to other words in the sentence.

### Putting It All Together

In essence, the self-attention mechanism allows the transformer to look at the entire sentence and determine which words are important to each other. It helps in forming a more accurate understanding of the meaning of each word by considering the full context. Just like a team of detectives who collaborate and focus on the most critical pieces of evidence to solve a case, the self-attention mechanism ensures that every word in the sentence gets the attention it needs to be understood in the context of the whole sentence.

### Encoder-Decoder Attention 🔄🔗

The encoder-decoder attention layer within the decoder acts as a bridge between the encoder and decoder. It allows the decoder to focus on different parts of the input sequence – an aspect critical for tasks like translation where the relevance of input and output segments can vary significantly.

This attention mechanism takes the output of the last layer of the encoder as its key and value, while the queries come from the previous decoder layer. This allows every position in the decoder to attend over all positions in the input sequence, which is crucial for accurate prediction and alignment between the input and the generated output.

These components work in concert within the transformer architecture, enabling it to handle a variety of complex sequence-to-sequence tasks with remarkable effectiveness.

<img src="../images/zxQyTK8quyYhd.jpg" alt="" width="300" height="auto">

[Link to video](https://www.youtube.com/watch?v=zxQyTK8quyY)

<img src="../images/bQ5BoolX9Aghd.jpg" alt="" width="300" height="auto">

[Lint to video](https://www.youtube.com/watch?v=bQ5BoolX9Ag)
