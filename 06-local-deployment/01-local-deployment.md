# Local Deployment for LLMs 🏠

When dealing with Large Language models, we have mainly seen how to use their APIs to send requests and receive their replies. And we also have seen how to fine-tune a model with the different approaches that can be used in this type o processes.

In this section, we'll talk about Local Deployment and its implementation, touching also the cons and pros of hosting open-source LLMs ourselves.

The idea of deploying a LLM locally can feels challenging compared to using an already made cloud-based system (like Chat-GPT4). But is not a process as tough as you can think, and it has a lot of benefits.

We'll start explaining you the pros and cons of this. Let us first give you the bad news:

## Cons
- best performing LLMs today (at December 2023) are not open-source, so you will get worse answers.
- best performing open-source LLMs are huge for most common computers (70GB models like Llama-2-70b requires 140GBs of VRAM)
> Note: you have already seen how quantization can help reduce by 8 the computational requirements, although this means losing quality.
- the latter point means that in order to have decently performing models you will need robust infrastructure.

## Pros
- complete control on how your data is being treated.
- saves you money for high-usage scenarios where continuous API calls to a cloud service would be expensive. So, by deploying your LLM locally, you make an initial investiment in hardware and software that is more economical in the long run, compared to the cost of cloud services.
- optimizes the usage of your local hardware resources, ensuring the model runs as efficiently as possible.
- you don't depend on an internet connection.

## In practice

There are several frameworks one can explore. Most of them can be used for proof of concept projects, but when building infrastructure, the only really useful framework is again LangChain. This is because every use-case will mean a minimum of structure. Nonetheless, other tools are much simpler to build and can help when checking if a project is viable or not. 

<img src="../images/5WCvGyPpWwghd.jpg" alt="" width="300" height="auto">

[Link to video](https://www.youtube.com/watch?v=5WCvGyPpWwg)

