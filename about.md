---
layout: page
title: 
permalink: /about/
---

I am a postdoc at Princeton's [PLI](https://pli.princeton.edu/). My aim is to develop language model systems that can autonomously complete tasks, such as software engineering, answering complex research-level questions, or finding cybersecurity vulnerabilities. I'm working towards this goal by building frontier-pushing benchmarks for LM systems (i.e. [SWE-bench](http://swe-bench.com), [CiteMe](https://citeme.ai), [SciCode](https://scicode-bench.github.io/), [AssistantBench](https://assistantbench.github.io/)) and then developing LM-based autonomous agents to solve these benchmarks (i.e. [SWE-agent](https://swe-agent.com), [EnIGMA](https://enigma-agent.com/), SWE-agent Multimodal).

<div class="imgcap">
<img src="/images/me.jpeg" style="width: 33%; height: 33%">
</div>

Our SWE-bench, which tests AI systems ability to solve real software issues from popular GitHub repositories, has [been downloaded more than 2 million times](https://pepy.tech/projects/swebench?timeRange=threeMonths&category=version&includeCIDownloads=true&granularity=daily&viewType=chart&versions=2.1.7%2C2.1.6%2C2.1.5), and there are teams at OpenAI, Meta, Google, Anthropic, and many other academic & industry groups that develop systems for SWE-bench. 
Our SWE-agent was the first open-source agent to beat the 10% accuracy threshold on SWE-bench, and is used by mutliple academic and industry teams, including at Anthropic, Meta, the Allen Institute for AI and others. 

Check out my [YouTube channel](https://www.youtube.com/@ofirpress/videos) for videos that explain my research and language modeling in general. 

##### People I've Worked With
During my postdoc I work with [Karthik Narasimhan's](https://www.cs.princeton.edu/~karthikn/) group at Princeton University. 

I completed my PhD at the Paul G. Allen School for Computer Science & Engineering at the University of Washington, where I was very fortunate to be advised by [Noah Smith](https://homes.cs.washington.edu/~nasmith/). For the last year of my PhD I was also a visiting scholar at [Kyunghyun Cho's](https://kyunghyuncho.me/) group at NYU. 

During my PhD I spent two years as a visiting researcher at Facebook AI Research Labs on [Luke Zettlemoyer's](https://www.cs.washington.edu/people/faculty/lsz) team where I mainly worked with [Mike Lewis](https://ai.facebook.com/people/mike-lewis/). Prior to that, in the summer of 2019 I interned at Facebook AI Research with [Omer Levy](https://levyomer.wordpress.com/). Towards the end of my PhD I spent half a year as a visiting researcher at [MosaicML](https://www.mosaicml.com/) on [Jonathan Frankle's](http://www.jfrankle.com/) team.

Before starting my PhD I completed my Bachelor's and Master's degrees in Computer Science at Tel Aviv University (where I was advised by [Lior Wolf](http://www.cs.tau.ac.il/~wolf/) and also worked with [Jonathan Berant](http://www.cs.tau.ac.il/~joberant/)). Between my Bachelor's and Master's degrees I was a software developer for a year.




##### My Background In Language Modeling

I've been writing papers on neural language modeling since 2016.  In the first six years of my career I focused on improving LM architectures without increasing their size or runtime. 

The weight tying method I developed is used today by many popular language and translation models, including OpenAI's GPT, Google's BERT, [Apple's on-device LM](https://arxiv.org/html/2407.21075v1), and the translation models of Google, Microsoft, Meta and Amazon. 

Our ALiBi method showed for the first time how to efficiently enable LMs to handle longer sequences at inference than the ones they were trained on. It has been adopted by BigScience's 176 billion parameter [BLOOM model](https://huggingface.co/bigscience/bloom), by the MPT series of models from MosaicML, by Replit's models and many others. 

In the final paper of my PhD we showed how to improve the ability of LMs to answer complex questions by simply using a better prompt. Our [self-ask](https://twitter.com/OfirPress/status/1577302733383925762) prompting method has the language model ask and answer sub-questions about the input question before generating the final answer. The structure of the self-ask prompt allows us to easily plug in Google Search to answer the sub-questions, which further improves performance. 


##### Misc.


My brother [Ori Press](https://oripress.com/) is a machine learning researcher. 

### Contact Me

[ofirp@princeton.edu](mailto:ofirp@princeton.edu)
<br>
[@ofirpress on Twitter](https://twitter.com/OfirPress)

### Mentees: 
[Carlos Jimenez](https://www.carlosejimenez.com/) (2023- , Princeton PhD) <br>
[John Yang](https://john-b-yang.github.io/) (2023- , Princeton MSc/RA) <br>
[Kilian Lieret](https://www.lieret.net/) (2023- , Princeton RE) <br>
[Talor Abramovich](https://www.linkedin.com/in/talor-abramovich-492a01214?originalSubdomain=il) (2024-2024, Tel-Aviv University MSc) <br>
[Muru Zhang](https://nanami18.github.io/) (2022-2023, University of Washington MSc) <br> 

### Selected Works ([Google Scholar](https://scholar.google.com/citations?user=LeHa8psAAAAJ), [Semantic Scholar](https://www.semanticscholar.org/author/Ofir-Press/40170001))

<span style="color:DarkRed">New (July 2024): Checkout our three new benchmarks: [CiteMe](https://citeme.ai), [SciCode](https://scicode-bench.github.io/), and [AssistantBench](https://assistantbench.github.io/)</span> <br>

[[SciCode]](https://scicode-bench.github.io/) <br>
Minyang Tian*, Luyu Gao*, Shizhuo Dylan Zhang, Xinan Chen, Cunwei Fan, Xuefei Guo, Roland Haas, Pan Ji, Kittithat Krongchon, Yao Li, Shengyan Liu, Di Luo, Yutao Ma, Hao Tong, Kha Trinh, Chenyu Tian, Zihan Wang, Bohao Wu, Yanyu Xiong, Shengzhu Yin, Minhui Zhu, Kilian Lieret, Yanxin Lu, Genglin Liu, Yufeng Du, Tianhua Tao, **Ofir Press**, Jamie Callan, Eliu Huerta, Hao Peng
NeurIPS 2024 <br>


[[AssistantBench]](https://assistantbench.github.io/) <br>
Ori Yoran, Samuel Joseph Amouyal, Chaitanya Malaviya, Ben Bogin, **Ofir Press**, Jonathan Berant <br>
EMNLP 2024 <br>

[[CiteME](https://www.citeme.ai/) <br>
Ori Press*, Andreas Hochlehnert*, Ameya Prabhu, Vishaal Udandarao, **Ofir Press**, Matthias Bethge <br>
NeurIPS 2024 <br>


[SWE-agent](https://swe-agent.com) <br>
John Yang*, Carlos E. Jimenez*, Alexander Wettig, Kilian Lieret, Shunyu Yao, Karthik Narasimhan, **Ofir Press** <br>
NeurIPS 2024 <br>
[[website]](https://swe-agent.com) <br>


[SWE-bench](https://swebench.com) <br>
Carlos E. Jimenez*, John Yang*, Alexander Wettig, Shunyu Yao, Kexin Pei, **Ofir Press**, Karthik Narasimhan <br>
ICLR 2024 (Oral) <br>
[[website]](https://swebench.com) <br>

[How Language Model Hallucinations Can Snowball](https://arxiv.org/abs/2305.13534) <br>
Muru Zhang, **Ofir Press**, William Merrill, Alisa Liu, Noah A. Smith <br>
ICML 2024 <br>
[[paper]](https://arxiv.org/abs/2305.13534) <br>

[Measuring and Narrowing the Compositionality Gap in Language Models](https://arxiv.org/abs/2210.03350) <br>
Ofir Press, Muru Zhang, Sewon Min, Ludwig Schmidt, Noah A. Smith, Mike Lewis <br>
Findings of EMNLP 2023 <br>
[[paper]](https://arxiv.org/pdf/2210.03350.pdf) [[code]](https://github.com/ofirpress/self-ask) [[datasets (Compositional Celebrities, Bamboogle)]](https://github.com/ofirpress/self-ask/tree/main/datasets) [[bib]](https://aclanthology.org/2023.findings-emnlp.378.bib) <br>
[[Self-ask & Self-ask + Google Search demo video, 2 min]](https://ofir.io/Self-ask-prompting/) <br>
[[The Compositionality Gap Explained (video), 2 min]](https://ofir.io/The-compositionality-gap-and-compositional-celebrities/) <br>
[[Introducing the Bamboogle Dataset (video), 2 min]](https://ofir.io/The-Bamboogle-Dataset/) <br>
[[In-depth overview of Self-ask and the Compositionality Gap (video), 47 min]](https://www.youtube.com/watch?v=NStW4fO0TII) <br>


[Train Short, Test Long: Attention with Linear Biases Enables Input Length Extrapolation](https://openreview.net/forum?id=R8sQPpGCv0) <br>
Ofir Press, Noah A. Smith, Mike Lewis <br>
ICLR 2022 <br>
<span style="color:DarkRed">ALiBi is the position embedding method of BigScience's BLOOM model, MosaicML's LMs, Replit's LMs, and many others.</span> <br>
[[paper]](https://openreview.net/pdf?id=R8sQPpGCv0) [[code]](https://github.com/ofirpress/attention_with_linear_biases) [[FAQ]](https://github.com/ofirpress/attention_with_linear_biases/#faq) [[bib]](https://github.com/ofirpress/attention_with_linear_biases#citation) <br>
[[Yannic Kilcher's video]](https://www.youtube.com/watch?v=-Kgxv64aG3o) [[My video (in-depth overview, 47 min)]](https://www.youtube.com/watch?v=Pp61ShI9VGc)
[[ICLR video (summarizes the important bits, 5 min)]](https://iclr.cc/virtual/2022/poster/6261)<br>

[Shortformer: Better Language Modeling using Shorter Inputs](https://aclanthology.org/2021.acl-long.427/) <br>
Ofir Press, Noah A. Smith, Mike Lewis <br>
ACL 2021 <br>
[[paper]](https://aclanthology.org/2021.acl-long.427.pdf) [[code]](https://github.com/ofirpress/shortformer) [[bib]](https://aclanthology.org/2021.acl-long.427.bib) <br> 
[[ACL video (summarizes the important bits, 12 min)]](https://screencast-o-matic.com/watch/cr1ZexV1tlA) 
[[video (detailed overview, 1 hour)]](https://www.youtube.com/watch?v=j9gl4txW4xo)<br>

[Improving Transformer Models by Reordering their Sublayers](https://www.aclweb.org/anthology/2020.acl-main.270/) <br>
Ofir Press, Noah A. Smith, Omer Levy <br>
ACL 2020 <br>
[[paper]](https://www.aclweb.org/anthology/2020.acl-main.270.pdf) [[summary]](https://ofir.io/Improving-Transformer-Models-by-Reordering-their-Sublayers/) [[code]](https://github.com/ofirpress/sandwich_transformer)  [[bib]](https://www.aclweb.org/anthology/2020.acl-main.270.bib) <br>
[[ACL video (summarizes the important bits, 12 min)]](https://slideslive.com/38928925/improving-transformer-models-by-reordering-their-sublayers) [[video (detailed overview, 35 min)]](https://www.youtube.com/watch?v=rFuuGEj3AhU)  <br>

[Language Generation with Recurrent Generative Adversarial Networks without Pre-training](https://arxiv.org/abs/1706.01399)  <br>
Ofir Press\*, Amir Bar\*, Ben Bogin\*, Jonathan Berant, Lior Wolf  <br>
1st Workshop on Learning to Generate Natural Language at ICML 2017 <br>
[[paper]](https://arxiv.org/abs/1706.01399) [[summary]](https://www.shortscience.org/paper?bibtexKey=journals/corr/PressBBBW17&a=ofirpress) [[code]](https://github.com/amirbar/rnn.wgan)  [[bib]](https://github.com/amirbar/rnn.wgan#reference) <br> 


[Using the Output Embedding to Improve Language Models](https://www.aclweb.org/anthology/E17-2025) <br>
Ofir Press, Lior Wolf <br>
EACL 2017 <br>
<span style="color:DarkRed">Introduced the **weight tying** method which is now used in GPT, BERT and many other state of the art language & translation models.</span> <br>
[[paper]](https://www.aclweb.org/anthology/E17-2025.pdf) [[summary]](https://www.shortscience.org/paper?bibtexKey=10.18653/v1/e17-2025&a=ofirpress) [[blog post]](https://ofir.io/Neural-Language-Modeling-From-Scratch/#weight-tying)  [[code]](https://github.com/ofirpress/UsingTheOutputEmbedding)  [[bib]](https://www.aclweb.org/anthology/E17-2025.bib) <br> 


#### Technical Reports
[Partially Shuffling the Training Data to Improve Language Models](https://arxiv.org/abs/1903.04167) <br>
Ofir Press <br>
Preprint, 2019 <br>
[[preprint]](https://arxiv.org/abs/1903.04167) [[code]](https://github.com/ofirpress/PartialShuffle) [[bib]](https://github.com/ofirpress/PartialShuffle#reference) <br>

[You May Not Need Attention](https://arxiv.org/abs/1810.13409)  <br>
Ofir Press, Noah A. Smith  <br>
Preprint, 2018 <br>
[[preprint]](https://arxiv.org/abs/1810.13409) [[summary]](https://www.shortscience.org/paper?bibtexKey=journals/corr/1810.13409&a=ofirpress)  [[code]](https://github.com/ofirpress/YouMayNotNeedAttention)  [[bib]](https://github.com/ofirpress/YouMayNotNeedAttention#reference)  <br> 

### Reviewing: 
NAACL: 2021, 2019 (secondary reviewer) <br>
EMNLP: 2022, 2021, 2019 (secondary reviewer) <br>
ACL: 2021, 2020 (secondary reviewer) <br>
EACL: 2021 <br>
NeurIPS: 2024, 2022, 2021 (emergency reviewer) <br>
ICLR: 2022 <br>
ICML: 2024 <br>
COLM: 2024 <br>
Journals: Harvard Data Science Review (2024) <br>
Workshops: SustaiNLP 2020, NeuralGen 2019 <br>

<!--
### ofir.io
As of January 2021, this site has been accessed by more than 60,000 people from 169 countries.
-->


