# Fine-tuning

Fine-tuning is one of the strongest oponents facing RAG. This technique excels at applications where we need the model to execute a specific task, like sentiment classification or having a specific behaviour. RAG, on the other hand, is the prefered technique for chat-related solutions as copilots, chatbots, etc. 

We have divided this module as follows:

0. Presection on [HuggingFace](00-HuggingFace.md): we first present to you HuggingFace, a model hub and model package that works "as the Github of LLMs". Basically, it hosts most common open-source models as well as some libraries that allow you to play with them.
1. Section on [fine tuning](01-fine-tuning.md): fine-tuning is not a straightforward method... specially if you want to do it locally, so we present a couple of modern techniques to get our models running.  

Fine-tuning requires a bit of extra knowledge regarding neural networks, you can take a look at the [llm basics section](../00-llm-basics/README.md) or at [DareData's Pytorch fundamentals Learning Pod](https://github.com/DareData/lp-pytorch-fundamentals).