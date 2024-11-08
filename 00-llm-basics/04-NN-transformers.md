# The building blocks of Large Language Models: Transformers ⚙️

Since you already know that Neural Networks only work with numbers, it is easy to understand that the first piece of the puzzle is tokenization. But how do we convert a bunch of tokens into a **meaningful** vector representation that contains the meaning nuances of the context of the sentence?

The answer: **Transformers**

Transformers are the pinacle structure when creating Neural Networks that form these Large Language models. At its core, the vanilla transformer model (the original Transformer architecture) consists of two primary components:

- **Encoders**: process the input sequence and create a set of representations that capture the nuances of the input data.
- **Decoders**: take these representations and generates an output sequence.

An essential feature of transformers is the use of **attention mechanisms** (mentioned slightly in the previous section), which allow the model to focus on different parts of the input sequence when producing the output, akin to how a human pays more attention to specific words while reading a sentence. This mechanism is pivotal in handling long-range dependencies in the data.
Another vital component that provides the model with information about the order of the sequence is **positional encoding**.


## Encoder Structure 📈🔍

The encoder of a transformer model is designed to parse the input sequence and convert it into a higher-dimensional space where relationships between the data points can be more easily discerned. It is typically composed of a stack of identical layers, each containing two main sub-layers:
- **self-attention layer**
- **position-wise fully connected feed-forward network**
  
Before the input is processed by this layers, it goes through two important steps:
- **Embedding Layer**
- **Positional Encoding Layer**
  
The embedding layer converts the input tokens into numerical vectors (what we call embeddings), while the positional encoding layer provides information about the order of the tokens in the sequence.
In turn, the self-attention layer allows the model to focus on different parts of the input sequence when encoding the data.


## Decoder Structure 📉🔎

The decoder in a transformer model mirrors the encoder with additional components specific to its role in generating the output sequence. It also consists of a stack of identical layers, but each unit has an additional sub-layer: **Encoder-Decoder Attention** that helps the decoder focus on appropriate segments of the input sequence.

The self-attention mechanism within the decoder allows each position in the decoder to attend to all positions in the decoder up to and including that position. Attention masks ensure that the predictions for a given position can depend only on the known outputs at positions before it, preserving the auto-regressive property.


# Self-Attention Mechanism 👀💡

The self-attention mechanism is what that allows a transformer to consider the entire input sequence simultaneously and to determine the relevance, or "attention" that each element of the input should receive when computing a representation of a particular word. This means that when the model is trying to understand one word, it looks at other words in the sentence to see which ones are important in giving the word its meaning.

Imagine you're reading a book and trying to understand the meaning of a particular word in a sentence. To do this effectively, you need to consider not just the word itself but also its context – the words around it. This is essentially what the self-attention mechanism does in a transformer model.

Self-attention works by creating three vectors for each input token: 
- **a Query Vector (Q)**: determines which other tokens in the sequence to focus on.
- **a Key Vector (K)**: represents the tokens that might be relevant to the current token.
- **a Value Vector (V)**: contains the actual information of the token that gets passed along if it is deemed relevant.

The query and key vectors may seem do the same function, but they have distinct roles: the Query Vector represents the token that is "asking" for information. And the Key Vector represents the tokens that might "answer" the query. Each key vector is compared with the query vector to determine how relevant the corresponding token is to the query.

The attention score is then computed by taking the dot product of the query with all keys, followed by a softmax operation to obtain the weights on the values.

So, in summary, the process follows the next steps: 
1. **Creating vectors**: generate query, key, and value vectors for each input token.
2. **Calculating Attention Scores**: compute the dot products between query vectors and key vectors to determine attention scores.
3. **Applying Softmax Operation**: normalize the attention scores using the softmax function to obtain weights.
4. **Computing the Weighted Sum**: multiply the value vectors by the attention weights and sum them to produce the final output for each token.

In essence, the self-attention mechanism allows the transformer to look at the entire sentence and determine which words are important to each other. It helps in forming a more accurate understanding of the meaning of each word by considering the full context. Just like a team of detectives who collaborate and focus on the most critical pieces of evidence to solve a case, the self-attention mechanism ensures that every word in the sentence gets the attention it needs to be understood in the context of the whole sentence.

# Positional Encoding 🌐📍

Positional encoding is a technique used to give the model information about the relative or absolute position of the tokens in the sequence. Since the self-attention mechanism does not inherently consider the order of the tokens, positional encoding is added to the input embeddings at the bottom of the encoder stack.

The original transformer paper proposed using sine and cosine functions of different frequencies to encode the positions. These functions provide a unique position signal to each token which can be scaled and manipulated along with the token embeddings through the layers of the transformer, thus preserving the order information.

# Encoder-Decoder Attention 🔄🔗

The encoder-decoder attention layer within the decoder acts as a bridge between the encoder and decoder. It allows the decoder to focus on different parts of the input sequence – an aspect critical for tasks like translation where the relevance of input and output segments can vary significantly.

This attention mechanism takes the output of the last layer of the encoder as its key and value, while the queries come from the previous decoder layer. This allows every position in the decoder to attend over all positions in the input sequence, which is crucial for accurate prediction and alignment between the input and the generated output.

These components work in concert within the transformer architecture, enabling it to handle a variety of complex sequence-to-sequence tasks with remarkable effectiveness.

<img src="../images/zxQyTK8quyYhd.jpg" alt="" width="300" height="auto">

[Link to video](https://www.youtube.com/watch?v=zxQyTK8quyY)


<img src="../images/bQ5BoolX9Aghd.jpg" alt="" width="300" height="auto">

[Lint to video](https://www.youtube.com/watch?v=bQ5BoolX9Ag)
