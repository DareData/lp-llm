# Summarization 📝

Summarization is one of the most important tasks for any LLM. Independently of if you are trying to build a summarizing app (_e.g._, to summarize customer's reviews or to create a description of an item) or if you want to construct something as a chatbot, it is crucial to get the summarization right. 


## The Value of Summarization 🕰️
Recognizing the overwhelming amount of text available today, summarization tasks and models help digest more content efficiently, reducing the time spent in procuring insights.

### Summarization in Software Applications 🖥️
Large language models are being integrated into apps for summarizing text. For example, you can summarize long articles or reports to capture the essence without reading the full text.


## Programming Summarization 🧑‍💻
You can utilize the to summarize text programmatically.
```python
"""
Your task is to generate a short summary of a product review in at most 30 words.
"""
```

### Tailoring Summaries for Specific Needs 🎯
You can also adjust your prompts to create summaries for your particular use-case. Imagine for example, that you want to address an specific business department
```python
"""
Focus on any aspects that mention shipping and delivery for feedback to the Shipping Department.
"""
```
or that you want to focus on highlighting aspects relevant to any specific department
```python
"""
Highlight any aspects relevant to the product's price and perceived value for the Pricing Department.
"""
```

### Extracting vs. Summarizing Information 🔍
Another application of summarizing, which could be consider an extreme version of summarization is extracting extracting key information.
```python
"""
Extract relevant information to give feedback to the Shipping Department.
"""
```

To see more about summarizing you can check the fourth part of the NG Course (Summarizing).

[Link to course](https://www.deeplearning.ai/short-courses/chatgpt-prompt-engineering-for-developers/)

## Inference Tasks with Language Models 🤔

In a similar fashion, one can define a slightly different task. Instead of summarizing or extracting information, one can use prompts to gather more abstract things about texts, for example, sentiments.
```py
"""
What is the sentiment of the following product review?

[Review Text]
"""
```

### Simplifying the Machine Learning Workflow ⚙️
Another use-case for these large language models is to bypass the traditional need for labeled datasets and model training for sentiment analysis or even use it just to perform the classification for the training dataset and build your own sentiment analysis model
```python
"""
Is the sentiment of this review positive or negative?
"""
```


You can even let the model decide by itself

```py
"""
List the emotions expressed in the following review: 
[Review Text].
"""
```

### Topic Inference 📚
Infer topics discussed in a piece of text for indexing or alerts. Of course, for most applications you would give the model a set of predefined topics and ask it to determine if it belongs to one or more topics.
```py
"""
Determine whether the following topics are covered in the text below: [Topic List].
"""
```

In the fifth part of the NG Course you'll learn about Inferring by analyzing sentiment and topics from product reviews and news articles.

[Link to course](https://www.deeplearning.ai/short-courses/chatgpt-prompt-engineering-for-developers/)
