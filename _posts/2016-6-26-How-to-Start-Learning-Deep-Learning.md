---
layout: post
title: How to Start Learning Deep Learning
---

Due to the recent achievements of artificial neural networks across many different tasks (such as [face recognition](https://research.facebook.com/publications/deepface-closing-the-gap-to-human-level-performance-in-face-verification/), [object detection](http://blogs.microsoft.com/next/2015/12/10/microsoft-researchers-win-imagenet-computer-vision-challenge/) and [Go](https://deepmind.com/alpha-go)), deep learning has become extremely popular. This post aims to be a starting point for those interested in learning more about it.

**If you already have a basic understanding of linear algebra, calculus, probability and programming:** I recommend starting with Stanford's [CS231n](http://cs231n.stanford.edu/). The course notes are comprehensive and well-written. The slides for each lesson are also available, and even though the accompanying videos were removed from the official site, re-uploads are quite easy to find online.

**If you don't have the relevant math background:** There is an incredible amount of free material online that can be used to learn the required math knowledge. [Gilbert Strang's course on linear algebra](http://ocw.mit.edu/courses/mathematics/18-06sc-linear-algebra-fall-2011/index.htm) is a great introduction to the field. For the other subjects, edX has courses from MIT on both [calculus](https://www.edx.org/course/calculus-1a-differentiation-mitx-18-01-1x) and [probability](https://www.edx.org/course/introduction-probability-science-mitx-6-041x-1).

**If you are interested in learning more about machine learning:** [Andrew Ng's Coursera class](https://www.coursera.org/learn/machine-learning) is a popular choice as a first class in machine learning. There are other great options available such as [Yaser Abu-Mostafa's machine learning course](https://work.caltech.edu/telecourse.html) which focuses much more on theory than the Coursera class but it is still relevant for beginners. Knowledge in machine learning isn't really a prerequisite to learning deep learning, but it does help. In addition, learning classical machine learning and not only deep learning is important because it provides a theoretical background and because deep learning isn't always the correct solution. 

**CS231n isn't the only deep learning course available online.** [Geoffrey Hinton's Coursera class "Neural Networks for Machine Learning"](https://www.coursera.org/course/neuralnets) covers a lot of different topics, and so does [Hugo Larochelle's "Neural Networks Class"](https://www.youtube.com/playlist?list=PL6Xpj9I5qXYEcOhn7TqghAJ6NAPrNmUBH). Both of these classes contain video lectures. [Nando de Freitas also has a course available online](https://www.cs.ox.ac.uk/people/nando.defreitas/machinelearning/) which contains videos, slides and also a list of homework assignments. 

**If you prefer reading over watching video lectures:** [Neural Networks and Deep Learning](http://neuralnetworksanddeeplearning.com/) is a free online book for beginners to the field. The [Deep Learning Book](http://www.deeplearningbook.org/) is also a great free book, but it is slightly more advanced.

**Where to go after you've got the basics:**

 - **Computer Vision** is covered by most, if not all, of the deep learning resources mentoined above. 
 - **Recurrent Neural Networks (RNNs)** are the basis of neural network based models that solve tasks related to sequences such as machine translation or speech recognition. [Andrej Karpathy's blog post on RNNs](http://karpathy.github.io/2015/05/21/rnn-effectiveness/) is a great place to start learning about them. Christopher Olah has a [great blog](http://colah.github.io/) where many deep learning concepts are explained in a very visual and easy to understand way. [His post on LSTM networks](http://colah.github.io/posts/2015-08-Understanding-LSTMs/) is an introduction to LSTM networks which are a wildly used RNN variant. 
 - **Natural Language Processing (NLP):** [CS224d](http://cs224d.stanford.edu/) is an introduction to NLP with deep learning. Advanced courses are available from both [Kyunghyun Cho](http://www.kyunghyuncho.me/home/courses/ds-ga-3001-fall-2015) (with lecture notes [here](https://github.com/nyu-dl/NLP_DL_Lecture_Note/blob/master/lecture_note.pdf)) and [Yoav Goldberg](http://u.cs.biu.ac.il/~yogo/nnlp.pdf).
 - **Reinforcement Learning:** If you'd like to control robots or beat the human champion of Go, you should probably use reinforcement learning. [Andrej Karpathy's post on deep reinforcement learning](http://karpathy.github.io/2016/05/31/rl/) is an excellent starting point. David Silver also recently published a short [blog post](https://deepmind.com/blog/deep-reinforcement-learning/) introducing deep reinforcement learning. 
 
 
**Deep learning frameworks:** There are many frameworks for deep learning but the top three are probably [Tensorflow](http://tensorflow.org/) (by Google), [Torch](http://torch.ch/) (by Facebook) and [Theano](http://deeplearning.net/software/theano/) (by [MILA](https://mila.umontreal.ca/en/)). All of them are great, but if I had to select just one to recommend I'd say that Tensorflow is the best for beginners, mostly because of the great [tutorials](https://www.tensorflow.org/versions/r0.9/tutorials/index.html) avialable. 

**If you'd like to train neural networks you should probably do it on a GPU.** You dont have to, but its much faster if you do. NVIDIA cards are the industry standard, and while most research labs use $1000 dollar graphics cards, there are a few affordable cards that can also get the work done. An even cheaper option is to rent a GPU-enabled instance from a cloud server provider like Amazon's EC2 (short guide [here](https://www.kaggle.com/c/facial-keypoints-detection/details/deep-learning-tutorial)).

Good luck!
