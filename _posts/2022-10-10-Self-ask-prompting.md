---
layout: post
title: Self-ask Prompting
mathjax: true
---
<iframe width="560" height="315" display=block src="https://www.youtube.com/embed/eXrNVnmxxAo" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
<br>
Self-ask is a new prompting method which improves the ability of language models to answer complex questions. 

Normally a question answering prompt looks like this:

```
Question: Who lived longer, Muhammad Ali or Alan Turing?
Answer: Muhammad Ali 

Question: When was the founder of craigslist born?
Answer: December 6, 1952

Question: Who was the maternal grandfather of George Washington?
Answer: Joseph Ball 

Question: Are both the directors of Jaws and Casino Royale from the same country? 
Answer: No
```

In self-ask, we first have the model generate and then answer sub-questions about the main input question, before answering the input question. So our prompt would look like so:

```
Question: Who lived longer, Muhammad Ali or Alan Turing?
Are follow up questions needed here: Yes.
Follow up: How old was Muhammad Ali when he died?
Intermediate answer: Muhammad Ali was 74 years old when he died.
Follow up: How old was Alan Turing when he died?
Intermediate answer: Alan Turing was 41 years old when he died.
So the final answer is: Muhammad Ali 

Question: When was the founder of craigslist born?
Are follow up questions needed here: Yes.
Follow up: Who was the founder of craigslist?
Intermediate answer: Craigslist was founded by Craig Newmark.
Follow up: When was Craig Newmark born?
Intermediate answer: Craig Newmark was born on December 6, 1952.
So the final answer is: December 6, 1952

Question: Who was the maternal grandfather of George Washington?
Are follow up questions needed here: Yes.
Follow up: Who was the mother of George Washington?
Intermediate answer: The mother of George Washington was Mary Ball Washington.
Follow up: Who was the father of Mary Ball Washington?
Intermediate answer: The father of Mary Ball Washington was Joseph Ball.
So the final answer is: Joseph Ball 

Question: Are both the directors of Jaws and Casino Royale from the same country? 
Are follow up questions needed here: Yes. 
Follow up: Who is the director of Jaws? 
Intermediate Answer: The director of Jaws is Steven Spielberg. 
Follow up: Where is Steven Spielberg from? 
Intermediate Answer: The United States. 
Follow up: Who is the director of Casino Royale? 
Intermediate Answer: The director of Casino Royale is Martin Campbell. 
Follow up: Where is Martin Campbell from? 
Intermediate Answer: New Zealand. 
So the final answer is: No
```

This leads the model to solve test-time questions by first answering subquestions about them, and this leads to an increase in performance. 

The structure of our prompt allows us to easily parse-out these subquestions and have Google Search answer them instead of the LM. We show that this further improves performance.
In our paper we call this system Self-ask + Search Engine. 
Note that Google Search does not have a publicly available API, and so we use [SerpApi](https://serpapi.com/), which is a cloud service that provides an easy to use API to Google Search. 

Watch our demo (embedded above) for a deeper overview of Self-ask and Self-ask + Google Search. 

Our paper is available [here](https://arxiv.org/abs/2210.03350), and our code for Self-ask + Google Search is [on GitHub](https://github.com/ofirpress/self-ask/blob/main/self-ask_plus_search-engine_demo.ipynb). 
