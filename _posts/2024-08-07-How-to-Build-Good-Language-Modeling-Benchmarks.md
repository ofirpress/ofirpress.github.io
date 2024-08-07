---
layout: post
title: How to Build Good Language Modeling Benchmarks
mathjax: true
---


Building benchmarks is important because they shine a spotlight on the weaknesses of existing language models and so can guide the community on how to improve them.

I’ve spent a lot of my career both on building benchmarks and on building systems that push forward the state-of-the-art on a given benchmark, and I believe that building good benchmarks is *just as important* as building new systems.  
  

Designing a good benchmark is challenging and I’ve spent a lot of time recently thinking about what makes for a good benchmark. I’ve distilled it down to three main properties:

  

#### 1.  Natural: 
Try to build a benchmark that has natural questions that some category of humans ask on a frequent basis. For example, the questions in our [SWE-bench](https://swe-bench.com) are made up of *real* bugs that users reported in popular GitHub repos. The task is to take the reported bug and the repo (as it was at the time the bug was reported) and try to fix the bug. That’s a very natural task that many people do on a daily basis (and even get paid for). Other natural tasks that we’ve recently turned into benchmarks include answering questions such as “What yoga studio near me has vinyasa classes before 8 AM on weekdays?” (see [AssistantBench](https://assistantbench.github.io/)) and “Which paper first showed that transformer language models can’t extrapolate to long sequences?” (see [CiteME](https://citeme.ai)).  
      
    

Sometimes I see new benchmarks come out that don’t fulfill the naturalness criteria, and they often have a hard time getting excitement from the community. I find benchmarks that contain IQ test-like questions, where you have to identify patterns in diagrams to not be very exciting. Or any ‘common sense’-like benchmarks that have questions like ‘Bob threw an egg at Alice’s face. Is Alice happy, sad, or ambivalent?’ These types of benchmarks might have been interesting in the past, when our LMs were still struggling with basic tasks, but now that our language models are becoming more capable, we need to challenge them with tougher and more realistic tasks.

Another way to think about whether a benchmark fulfills the naturalness criteria is to evaluate whether it fulfills what I term the usefulness criteria: would a system that got better-than-baseline accuracy on this benchmark be useful to humans? Would it make anyone more productive? A system that can autonomously fix bugs would save lots of time for developers, even if it only managed to fix the easiest ten percent of bugs. A system that can quickly find me a yoga class that meets my needs would save me time.

  

I’ve also noticed that there are two simple indicators for a benchmark being unnatural, and so I try to avoid building benchmarks that have these properties:

A.  **The question set-up is unrealistic**: For example, if a benchmark contains multiple choice questions, I believe it is unnatural. When I go to the doctor, I never say “Doctor doctor, my elbow hurts, and it is definitely happening because of one of these *four* options…”. Always think of your question set-up and if it seems unrealistic, try to modify it.
    
B.  **The questions are made up and not taken from actual questions asked by actual humans**: If you work for Google and you’re tasked with building a challenging question-answering benchmark, a really nonoptimal thing to do would be to sit around by yourself in a room and just try to think of questions. You’d probably come up with weird questions that no real user would ever ask. A really smart thing to do would be to look at the Google Search logs and try to filter it to find questions that users entered and did not find a good answer to (for example, this might be indicated by the user going to the second result page or because the user spent more than five minutes on the initial results page).  

SWE-bench contains real bug reports filed by real users on real GitHub repos. I think this makes the benchmark much more exciting to the community. Using questions that actual users asked implies that by building systems that get higher scores on the benchmark, we would be fulfilling a real-world need.
    

#### 2.  Automatically Evaluateable: 
In a benchmark, given a model-generated answer to a question, we need to determine if the model was right or wrong. Sometimes this is easy, but depending on the question type, this could be hard or impossible. Validating the correctness of code could be a challenging task, since there are many different ways to program a given function, and that’s why benchmarks such as HumanEval and SWE-bench use unit tests to automatically validate code.  

Summarization is a task that I think could be super useful for humans (“Write a 500 word summary of this patient’s medical file”) but we’ve seen very little development of new benchmarks in this space because evaluation is just so hard. There are many different ways to correctly summarize a given text, but evaluating these summaries is hard. Some have proposed using an LM to evaluate LM outputs but I don’t think that that’s the right way to go. We should either use an LM to solve a task, or use it to judge outputs, but if we use it as both the solver and the evaluator that leads to problems.
    

#### 3.  Challenging
If you launch an automatically evaluatable and natural benchmark, but the accuracy of the best LM at launch is 80%, people will see your benchmark as already being *solved* and won’t want to try and build models to improve performance on it. I think making your benchmarking challenging is critical. I think that at launch, a good benchmark should have the top LMs achieving between 1% to 35% accuracy on it.
    
If you find a benchmark idea and build it out and it’s natural and automatically evaluateable but you build a baseline and it gets 70% right, one thing you might want to consider doing is to use that baseline to **filter-out the easier instances** in the benchmark. For example, our [Bamboogle benchmark](https://ofir.io/The-Bamboogle-Dataset/) had tough-to-answer 2-hop questions, and we built the dataset by filtering out all questions that Google Search answered correctly. For CiteME, we filtered out all questions that GPT-4o managed to answer correctly in a prompting-only setting (i.e. non-agentic). I think that building benchmarks by finding tasks that a baseline approach can’t solve is a great way to go.

  

Beware- researchers are humans and humans have emotions. If at launch, the top model’s accuracy is less than 10%, that might seem very intimidating for most researchers, and they might not want to work on your benchmark at all. Try to plan for that. For example, when we launched SWE-bench the top model’s accuracy was 1.96%. Almost everyone I talked to at the time was intimidated by this and didn’t want to approach it. I wasn’t worried, because we immediately started working on SWE-agent after releasing SWE-bench. I remember telling the team that if we got anywhere near 10% accuracy, the community would see that SWE-bench isn’t as impossible as it seemed, and that would get the ball rolling. Eventually we launched SWE-agent at around 13% accuracy and soon afterwards a barrage of other models appeared, each getting better accuracy than the previous one.

  
  
  

#### Bonus Property: 

Building a benchmark that would be **hard to leak into the training data** is something that I think about all the time. Could we build a benchmark such that even if the benchmark itself leaks into an LM’s training data, it won’t really help that LM in getting a good score on the benchmark? In [SciCode](https://scicode-bench.github.io/), we had PhDs write very tough programming challenges related to their field of study. Each instance in the dataset is a description of a function and the unit tests to validate whether the model programmed it correctly or not. We intentionally *do not* release any of the answers to these programming challenges, to make sure these answers are never inserted into any LMs training data. This way, even if our benchmark fully leaks into an LM’s training set, it still won’t be able to produce the right answers to the questions. Achieving this property is extremely difficult, and so it’s not something I try to do with every single benchmark I build.

  

#### Other guidelines:

1.  Have **one** number for your benchmark. One metric that people go for. “We get 87% on HumanEval” is the vibe you are going for. Don’t have three metrics, like accuracy, precision, and recall, have just one. Don’t divide accuracy by category, have just an overall accuracy. This is really important. You want to make use of your benchmark as easy as possible. You want people to *get it* right away. If you start having seventeen metrics and nineteen categories it’s going to be complicated for people to understand what you’re trying to do, and that will lower the chances of your benchmark catching on.  
      
    When you write the analysis section in your paper about your benchmark, it’s totally fine to present other metrics for each model, or to break down performance by category, but you should only do that there, and not have the categories or other metrics when you generally talk about the benchmark.
    
2.  When you write a paper, always include very strong baselines, both based on strong proprietary models and on leading open source models. You should never try to make your benchmark look more impressive than it actually is by including only weak baselines, or baseline systems that use old or outdated models like GPT 3.5 or Llama 3 7B.
    
3.  Benchmarks typically get saturated within a year. And so when you build a benchmark, I don’t think it’s important to worry about questions like “Will this still be an interesting question in five years?”. Deep learning moves incredibly quickly, and there’s no way to predict where we’ll be in more than a year. For this reason, it’s also OK to have benchmarks that ask questions that will probably have totally different answers in a year or two, such as “Which yoga studios near Bushwick in NYC have a Vinyasa class before 7AM?”.
    

  

Benchmarks are great because they provide a lot of room for creativity, and they can be super impactful in guiding the community towards the future. I hope this post helps you in building the next big LM benchmark. And always remember- rules are meant to be broken. I do not think that a benchmark that does not follow all of these rules is bad. I just think that these guidelines are a good indicator for whether you're on the right path or not. 

  

If you enjoyed this post, please join our [upcoming event](https://lu.ma/4240w5us) on Wednesday, the 14th of August, where we will present the three new benchmarks my collaborators and I have recently launched: SciCode, CiteME, and AssistantBench.
