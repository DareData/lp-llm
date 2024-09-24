# Chain of Thought (CoT) 🔗🧠

Chain of thought prompting is a technique used in interacting with AI models, particularly language models, where the user structures their query to lead the AI through a step-by-step reasoning process. This method helps the AI to better understand complex problems by breaking them down into smaller, more manageable parts. Essentially, it's like guiding the AI to 'think aloud' as it works through the problem, providing a clearer path to the final answer.

For example, instead of asking this question:

```python
"""
Which is a faster way to get to work?
Option 1: Take a 1000 minute bus, then a half hour train, and finally a 10 minute bike ride.
Option 2: Take an 800 minute bus, then an hour train, and finally a 30 minute bike ride.
"""
```
you can use a chain-of-thought reasoning to improve the output of the answer:

```python
"""
Which is a faster way to get home?
Option 1: Take an 10 minutes bus, then an 40 minute bus, and finally a 10 minute train.
Option 2: Take a 90 minutes train, then a 45 minute bike ride, and finally a 10 minute bus.
Option 1 will take 10+40+10 = 60 minutes.
Option 2 will take 90+45+10=145 minutes.
Since Option 1 takes 60 minutes and Option 2 takes 145 minutes, Option 1 is faster.

Which is a faster way to get to work?
Option 1: Take a 1000 minute bus, then a half hour train, and finally a 10 minute bike ride.
Option 2: Take an 800 minute bus, then an hour train, and finally a 30 minute bike ride.
"""
```

<img src="../images/sYKU9zC5RKshd.jpg" alt="" width="300" height="auto">

[Link to video](https://www.youtube.com/watch?v=sYKU9zC5RKs)
