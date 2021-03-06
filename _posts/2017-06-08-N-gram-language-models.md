---
layout: post
title: "N gram language models"
comments: true
description: "N gram language model explaination"
keywords: "nlp, n gram language, language , natural language"
---

#N-gram Language Models

**N-gram modelling** is one of the basic concept in NLP. It is a type of probabilistic language model for predicting the next item in the sequence of words ( sentence ).\\
Some of the applications of this model are :

1. **Context Sensitive Spelling Correction**

For example, consider the following two sentences 
_about five minutes from_ **and** _about five minuets from_ . \\
Here, the words _minutes_ and _minuets_ have meaning and they are in my set of vocabulary. But the probability of _minutes from_ is more than _minuets from_. This is called context sensitive spelling correction.
 Here it should be

> **_P(about five minutes from) > P(about five minuets from)_**

2. **Speech recognition**

When you speak a sentence like **I saw a van** then,

>**_P(I saw a van) > P(eyes awe of an)_**

There are many more applications in Machine transalation , predicting the completion of a sentence ( Predict text input system) etc.


***
Our goal is to compute the probability of sequence of words.
>P(w) = p(w1,w2,w3,...,wn).

Now, from the Bayes theorem we already have the idea that\\
**P(B|A) = P(A,B)/P(A)**\\
that implies,\\
**P(A,B) = P(A) * P(B|A)**\\
similarly ,\\
**P(A,B,C) = P(A) * P(B|A) * P(C|A,B)**\\
This is called chain rule. We can generalise this formula as \\
`P(x1,x2,...,xn) = P(x1) * P(x2|x1) * P(x3|x1,x2)......P(xn|x1...xn-1)` \\

We may never see enough data for estimating these probability values. Therefore according to Markov's assumption we use only upto _k_ words in the sentence.
According to **Kth Order Markov Model** and using **Chain rule** we derive at

`P(w1,w2,w3....wn) ~ π P(wi | wi-k......wi-1)`

***
A **N-gram model** uses only _n-1_ words of prior context.\\
An n-gram of size 1 is referred to as a **"unigram"**. Eg- P(office)\\
 size 2 is a **"bigram"** (or, less commonly, a **"digram"**). Eg- P(office|from)\\
 size 3 is a **"trigram"**. Eg-P(office| minutes from) \\
Larger sizes are sometimes referred to by the value of n in modern language, e.g., **"four-gram"**, **"five-gram"**, and so on.
