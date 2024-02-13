---
layout: post
title: 5 Tips for Finding Research Topics
mathjax: true
---



I’ve spent the past eight years doing research on neural language models. While my top-level goal of making language models more useful to humans has remained stable, my path to achieving it has changed over time. I’ve learned that in research, you not only have to learn how to execute on a given idea, but you also have to learn how to pick which direction to direct your efforts at. 

This post contains five patterns that I’ve noticed that both my peers and I use to think of new ideas for research projects. It’s important to note that this advice might only apply to the research sub-field that I’m in and might only apply to people who want to perform research in a manner that is similar to the one I use. There are many ways to succeed, some of which are orthogonal to the guidelines that I use.




### 1. **Focus first on finding a problem, not a solution.** 
A common mistake I see people do is start a project by thinking about a model they want to build, without even thinking about whether it’s even necessary. They’ll get really excited about a certain method and try to just build something based on that. “Let’s build a retrieval-augmented language model!”. “I want to build an LM agent that uses reinforcement learning!”. But I don’t really think that research can be done with such a vague goal. In order to ground your research, I believe that it’s incredibly useful to find a specific issue that the community would care about, and then work from there. So for example “I’ve noticed that GPT has a really hard time answering questions that have a spatial component” or “I’ve noticed that GPT has a really hard time programming solutions to programming puzzles about graphs” are good starting points. First define an issue, then try to figure out if it would interest the community, then build a dataset of example problems and then try to build a model that solves them. While building a solution, if you figure out that you do need RL or retrieval, then integrate that into your solution. But you’ll always be grounded in the results you’ll get from running your various baselines and new models on the dataset that you built. That’ll tell you whether those components are actually improving your model or not. 
I used to think that the majority of the work for researchers in deep learning was in building solutions, but I’m now pretty convinced that **the majority of the work is in finding  good problems**!


### 2. **It’s better to iterate and experiment through many ideas that are maybe good rather than working through one or two ideas that are “definitely” correct.**
The king of deep learning is empirical results. Once you’ve decided which problem to focus on, the only thing that you can do if you want to test a certain solution is to run it and see what happens. Therefore, for me it has been very beneficial to iterate through the idea-brainstorming-to implementation-to-results cycle many times per project. I sometimes see people get stuck in endless pontification and over-analysis of ideas without ever opening an IDE. They’ll think of an idea and then analyze it on a whiteboard for weeks before they even consider sitting down to program it. In my view, that hypothetical analysis is not very useful. Since there’s not really a theory of deep learning yet, the utility of analyzing potential solutions on a whiteboard for more than a few hours is not much. As ML practitioners, our source of truth is the results we get after running an experiment. Yes, you shouldn’t just program every single idea that comes into your head, but also, once you think of something and spend an hour or two thinking it through, just implement it and see how it does. 

Only many empirical experiments will build an intuition for what works and what doesn’t and will help you define the path forward. Quick iteration through a trajectory of research ideas leads to progress in deep learning. I’ve also observed that one of the most important factors is the number of iterations on research ideas and *not* the magnitude of each idea. So I generally recommend thinking of and working on solutions that are as simple as possible, so that you can go through the idea-brainstorming-to implementation-to-results cycle as many times as possible per project. Understanding what ideas to implement and which ones not to, how to prioritize different possible directions, and how to reject ideas before even implementing them are skills that you will learn as you spend more time doing research. 

In the second year of my PhD I had an idea for a new type of retrieval-augmented LM. This model had two components, a retrieval and an LM. The LM was pretty much off-the-shelf, and the retriever was the component that I wanted to innovate on. The full model was quite complex and so the first prototype took me about three months to build. I then ran it and it didn’t improve performance. So I then thought of a second version, which was also quite complex and ended up taking me two months to program. That model didn’t work either. 

I then realized that I should first verify if this idea could even work by using an oracle retriever: basically cheating at the retrieval stage to make your retriever as good as it could be. This oracle-based model took a few days to program. When I ran it, it also didn’t work, thereby making my confidence in the overall idea tank. If the model couldn’t work with an impossibly-powerful (enabled by cheating) retriever, I didn’t think it could work with a less powerful, but possible, retriever.
In hindsight, when I had the original idea, I wish I would’ve been able to notice that the initial prototype would’ve taken three months to program, and instead of starting from it, it would’ve been much smarter to start from the much smaller oracle prototype, and only successively build my way up to the three-month prototype, only if the earlier prototypes showed promise. That would've saved me a lot of time. 

### 3. **Write a paper that many people would want to read:** 
Your paper should either teach us something new about an existing system, method or benchmark, or achieve better performance on an existing benchmark, or present a new benchmark. Good papers sometimes do two of those things. 

#### What does it mean to achieve better performance?
If I have a model that can get 70% accuracy on SWE-bench, and you develop a new one that achieves 72% accuracy but is three times slower then that’s probably not an interesting new system. Improving performance doesn’t just mean improving accuracy and ignoring all other factors. When we look at a system, we have to observe both accuracy but also training time, inference time, memory usage, latency and disk space usage. For a new system to be better than an old one, it should improve on one of these metrics while keeping the other ones at the same level or better. If the improvement is substantial, it’s fine to disregard this rule, and for example, present a system that achieves 99% accuracy on SWE-bench while being 30% slower than the current state-of-the-art. But in that case, make sure to compare your method to the baseline, when the baseline is given 30% more time. 
You should always be comparing your methods to the strongest baselines you can find, and you should strive to make that comparison as fair as possible. 

#### Why is community excitement important?
You should definitely work on research that excites you, but you should also try to find a topic that would also excite a large amount of the other researchers in the field. Papers only reach a small percentage of their target audience. If you’re writing a paper about a niche topic that only has 50 researchers working on it, maybe 15 of them would actually hear about your work, 5 of them would read it and likely none of them would perform follow-up work. I therefore find it incredibly useful and rewarding to work on topics that have a wide interest in the community. 


### 4. Write a paper that would be an interesting part of the research discourse that will be happening in nine months.
In my experience, for my style of work, research projects take nine months on average. That means that when you start thinking of ideas you shouldn’t think of ideas that would be interesting if they were published today or tomorrow, because it’s going to take you much longer than that to write a paper. You should definitely make sure that you’re not writing a paper that would have been relevant one or two years ago. One simple rule of thumb is to make sure that at least some of the related works that you’re citing are from the past year or two. If your latest citation is from five years ago, there’s a big chance that you may be writing a paper that would be irrelevant to the current research discourse. 

The most important skill to learn here is observing the trajectories that occur within your research sub-community and being able to predict where they will go. As you do research for more time you’ll get better at predicting where your research field is heading and how to do work that will fit into that puzzle as well as possible. It sounds impossible at first but I believe that, at least in deep learning, it’s possible to predict with high accuracy where the field will be in 9 months. It’s totally impossible to predict where the field will be in 18 months or longer, and that’s why I recommend not working on projects that would take that long.

### 5. Keep it simple. 
And what do I mean by ‘it’? **Everything.** Try to work on problems that are easy to describe. Try to find simple solutions for those problems. Try to describe your solution in your paper in as simple of a way as possible. Try to write the code for your method in a simple way, and make it easy for others to run and extend your code. 

Think of the counterexample here. If you worked on a problem that took two pages to describe in a paper, would any reader stick around for that whole description, let alone would anyone stick around to read about your solution? I also feel like most of the most important problems in our field can be stated in a sentence, so if it takes you six paragraphs to describe the problem you’re working on, that might be a hint that you’re working on a problem that is too niche or contrived. 

It makes me happy when lots of people get excited by the work I release. Simplicity is one of the main driving factors in finding ideas that lots of people might get excited by. If you work on a super complex topic, there’s a high chance that very few people would even understand the problem you’re trying to solve, let alone your solution. 

As for keeping your solution simple- the ML community has proven time and time again that the best methods that have the most long-lasting impact are always the simplest ones. 

As with all rules, in some cases it does make sense to violate this rule. Tim Dettmers’ bitsandbytes is a super popular efficiency library. It’s made up of a lot of very non-simple CUDA code. But everything else about this library is extremely simple: it’s really easy to use, and the motivation behind it is very clear (“bitsandbytes helps you run big models on small GPUs”).

As a researcher that has to publish, it may be tempting to find complex solutions to complex problems, since [reviewers are frequently impressed when they see many equations and proofs in a paper](https://twitter.com/andrewgwils/status/1751746057036234963). But in my experience, while those types of papers may initially get accepted, over time, complex solutions do not have much lasting impact. Complex papers are harder to read, and their code is usually harder to extend; these properties substantially harm impact. 

#### Closing note:
The strength of the research community is in its large size and diversity. There are many ways to do good research, some of which align with the tips above and some of which don’t. I hope that by sharing these lessons that I’ve learned over the years I’ve helped you improve your ability to do the best research you can.

If you enjoyed this post, you might also enjoy [my post on tips for junior researchers](https://ofir.io/Tips-for-Junior-Researchers/), which focuses on *how* to do research and how to work with a mentor.

Thank you to Nelson Liu, Will Merrill, Samuel Ainsworth, Shunyu Yao and Naomi Saphra for comments on previous drafts of this post.










