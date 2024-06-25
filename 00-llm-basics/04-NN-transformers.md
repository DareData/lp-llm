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

The self-attention mechanism is what allows a transformer to consider the entire input sequence simultaneously and to determine the relevance, or "attention" that each element of the input should receive when computing a representation of a particular word.

In essence, it computes a score that signifies how much focus should be put on other parts of the input when encoding a certain part.

Self-attention works by creating three vectors for each input token: 
- a query vector
- a key vector
- a value vector

The attention score is then computed by taking the dot product of the query with all keys, followed by a softmax operation to obtain the weights on the values.

### Encoder-Decoder Attention 🔄🔗

The encoder-decoder attention layer within the decoder acts as a bridge between the encoder and decoder. It allows the decoder to focus on different parts of the input sequence – an aspect critical for tasks like translation where the relevance of input and output segments can vary significantly.

This attention mechanism takes the output of the last layer of the encoder as its key and value, while the queries come from the previous decoder layer. This allows every position in the decoder to attend over all positions in the input sequence, which is crucial for accurate prediction and alignment between the input and the generated output.

These components work in concert within the transformer architecture, enabling it to handle a variety of complex sequence-to-sequence tasks with remarkable effectiveness.

<img src="../images/zxQyTK8quyYhd.jpg" alt="" width="300" height="auto">

[Link to video](https://www.youtube.com/watch?v=zxQyTK8quyY)

<img src="../images/bQ5BoolX9Aghd.jpg" alt="" width="300" height="auto">

[Lint to video](https://www.youtube.com/watch?v=bQ5BoolX9Ag)
