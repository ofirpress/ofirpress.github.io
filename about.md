---
layout: page
title: 
permalink: /about/
---

I am a PhD candidate (ABD) at the Paul G. Allen School for Computer Science & Engineering at the University of Washington, where I am very fortunate to be advised by [Noah Smith](https://homes.cs.washington.edu/~nasmith/). 
During my PhD I spent two years as a visiting researcher at Facebook AI Research Labs on [Luke Zettlemoyer's](https://www.cs.washington.edu/people/faculty/lsz) team where I mainly worked with [Mike Lewis](https://ai.facebook.com/people/mike-lewis/). In the summer of 2019 I interened at Facebook AI Research with [Omer Levy](https://levyomer.wordpress.com/). 

My research focuses on figuring out what scale doesn't solve in neural language modeling and finding out how we can improve LMs without scaling up the number of parameters, runtime, or memory usage. The weight tying method I developed is used today by almost all big language and translation models. Our more recent Shortformer paper showed that language models, when evaluated correctly, don't actually benefit from training on inputs that are more than 1k tokens long. Finally, my most recent paper, ALiBi, shows for the first time how to efficiently enable LMs to handle longer sequences at inference than the ones they were trained on. It has been adopted by BigScience's 176 billion parameter [BLOOM model](https://huggingface.co/bigscience/bloom). 

<div class="imgcap">
<img src="/images/me.jpeg" style="width: 33%; height: 33%">
</div>

Previously, I completed my Bachelor's and Master's degrees in Computer Science at Tel Aviv University (where I was advised by [Lior Wolf](http://www.cs.tau.ac.il/~wolf/) and also worked with [Jonathan Berant](http://www.cs.tau.ac.il/~joberant/)) and briefly worked as a software developer. 

My brother [Ori Press](https://oripress.com/) is a computer vision researcher. 

### Contact me

[ofirp@cs.washington.edu](mailto:ofirp@cs.washington.edu)
<br>
[@ofirpress on Twitter](https://twitter.com/OfirPress)

### Papers ([Google Scholar](https://scholar.google.com/citations?user=LeHa8psAAAAJ))

[Train Short, Test Long: Attention with Linear Biases Enables Input Length Extrapolation](https://openreview.net/forum?id=R8sQPpGCv0) <br>
Ofir Press, Noah A. Smith, Mike Lewis <br>
ICLR 2022 <br>
[[paper]](https://openreview.net/pdf?id=R8sQPpGCv0) [[code]](https://github.com/ofirpress/attention_with_linear_biases) [[bib]](https://github.com/ofirpress/attention_with_linear_biases#citation) <br>
[[Yannic Kilcher's video]](https://www.youtube.com/watch?v=-Kgxv64aG3o) 
[[ICLR video (summarizes the important bits, 5 min)]](https://iclr.cc/virtual/2022/poster/6261)<br>

[Shortformer: Better Language Modeling using Shorter Inputs](https://aclanthology.org/2021.acl-long.427/) <br>
Ofir Press, Noah A. Smith, Mike Lewis <br>
ACL 2021 <br>
[[paper]](https://aclanthology.org/2021.acl-long.427.pdf) [[code]](https://github.com/ofirpress/shortformer) [[bib]](https://aclanthology.org/2021.acl-long.427.bib) <br> 
[[ACL video (summarizes the important bits, 12 min)]](https://screencast-o-matic.com/watch/cr1ZexV1tlA) 
[[video (detailed overview, 1 hour ]](https://www.youtube.com/watch?v=j9gl4txW4xo)<br>

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
NeurIPS: 2022, 2021 (emergency reviewer) <br>
ICLR: 2022 <br>
Workshops: SustaiNLP 2020, NeuralGen 2019 <br>

<!--
### ofir.io
As of January 2021, this site has been accessed by more than 60,000 people from 169 countries.
-->


