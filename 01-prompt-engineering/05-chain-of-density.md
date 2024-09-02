# Chain-of-Density (CoD) 🔗⚖️

LLMs have the tendency of not being very good on a first-base iteration unless taken from the hand. In particular, one of the things they are good at, but do not excel is when receiving large chunks of text. They pay a lot of attention to the beginning and end of the prompts, but get lost in the middle.

An example of this lack of performance happens when dealing with summarization of large chunks of text. 
Implementing CoD involves the use of a series of chained prompts that guide the model in generating a summary. 

The Chain-of-Density (CoD) prompts try to solve this issue by addressing the model's focus, directing it toward essential information and away from irrelevant details. This is normally achieved by iterating over:
- a simple task divided in steps
- a final step in which the model has to determine what it missed


For example, you might start with a general prompt for summarization and then follow up with specific prompts to adjust the density of the generated text.

 
```python
"""
Article: {{ARTICLE}}
You will generate increasingly concise, entity-dense summaries of the above Article.

Repeat the following 2 steps 5 times:

Step 1. Identify 1-3 informative Entities (";" delimited) from the Article which are missing from the previously generated summary.
Step 2. Write a new, denser summary of identical length which covers every entity and detail from the previous summary plus the Missing Entities.

A Missing Entity is:
- Relevant: to the main story.
- Specific: descriptive yet concise (5 words or fewer).
- Novel: not in the previous summary.
- Faithful: present in the Article.
- Anywhere: located anywhere in the Article.

Guidelines:
- The first summary should be long (4-5 sentences, ~80 words) yet highly non-specific, containing little information beyond the entities marked as missing. Use overly verbose language and fillers (e.g., "this article discusses") to reach ~80 words.
- Make every word count: rewrite the previous summary to improve flow and make space for additional entities.
- Make space with fusion, compression, and removal of uninformative phrases like "the article discusses".
- The summaries should become highly dense and concise yet self-contained, e.g., easily understood without the Article.
- Missing entities can appear anywhere in the new summary.
- Never drop entities from the previous summary. If space cannot be made, add fewer new entities.
Remember, use the exact same number of words for each summary.
Answer in JSON. The JSON should be a list (length 5) of dictionaries whose keys are "Missing_Entities" and "Denser_Summary".

"""
```

<img src="../images/idknpGjs2-Ihd.jpg" alt="" width="300" height="auto">

[Link to video](https://www.youtube.com/watch?v=idknpGjs2-I)


