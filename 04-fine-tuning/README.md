# Fine-tuning

Fine-tuning is one of the strongest oponents facing RAG. This technique excels in applications where we need the model to execute a specific task, such as sentiment classification or perform a specific behaviour. On the other hand, as discussed in the last section, RAG is the prefered technique for chat-related solutions like copilots or chatbots.

Fine-tuning is the process of taking a pre-trained language model and training it on a specific dataset to specialize it for a particular task or domain. This involves adjusting the model's weights to adapt it to new data while mantaining the general language comprehension gained during the initial pre-training phase.

Various libraries, such as Hugging Face’s Transformers, TensorFlow, and PyTorch, provide tools that make fine-tuning more accessible.

We have divided this module as follows:

0. [Fine tuning](00-fine-tuning.md): fine-tuning is not a straightforward process... especially if you want to do it locally. In this section, we present a few modern techniques to get the models running.

1. [HuggingFace](01-HuggingFace.md): in this section we introduce HuggingFace, a model hub and package that works as the "Github of LLMs". Basically, it hosts the most common open-source models, as well as some libraries that allow you to play with them. 

2. [Practical examples](examples): example notebooks demostrating fine-tuning implementation using both a model and dataset from Hugging Face. The goal is to walk you through the steps of applying fine-tuning using LoRa.


> Fine-tuning requires a bit of extra knowledge regarding neural networks, you can take a look at the [llm basics section](../00-llm-basics/README.md) or at [DareData's Pytorch fundamentals Learning Pod](https://github.com/DareData/lp-pytorch-fundamentals).
