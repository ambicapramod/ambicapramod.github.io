---
layout: post
title: "Good-Turing and Kneser-Ney Smoothing Techniques"
comments: true
description: "smoothing techniques explaintaion"
keywords: "nlp, n gram language, language , natural language,smoothing, techniques"
---
#Smoothing Techniques
In this blog you will be learning about two most commonly used smoothing techniques that are used in NLP for probability distribution.This is used in reducing of canceling the effect due to random variation.
##Good-Turing Smoothing :
###Intution: 
We use the count of things we have seen once to estimate the count of things we have never seen.
####Idea:
The idea is to **reallocate** the probability mass of _n_-grams that occur _r+1_ times in the training data to the _n_-grams that occur _r_-times.<br>
In particular, reallocate the probability mass of _n_-grams that were seen once to _n_-grams that were never seen.<br>
for each count c, an adjusted count \\(c^* \\) (Effective count) is computed as :<br>
$$ c^* = \dfrac{ {(c+1)} \times Nc} {N_{c+1}}$$

Where \\(Nc\\)  is number of _n_-grams seen exactly _c_ times.

***
##Kneser-Ney Smoothing :

####Intution:
Given  words , We'll see what other words it comes with.<br>
It is used for the better estimate for probabilities of lower-order unigrams! 
\\(P_{continuation}(w)\\) : " How likely is word **w** to appear as the novel continuation " 

Here we have,
\\( P_{continuation} \propto |{ w\_{i-1}: c(w\_{i-1},w)>0}|\\) 

After Normalization we get,
$$P_{continuation}w(i) = \dfrac{ |{w\_{i-1} : c(w\_{i-1},w)>0}|} {|(w\_{j-1},w\_j):(w\_{j-1},w\_j)>0|}$$

therefore , we derive at **Kneser-Ney smoothing**:
$$P_{KN}(w\_i | w\_{i-1}) = \frac{ max(c(w\_{i-1},w\_i)-d,0)} {c(w\_{i-1})}+\Lambda(w\_{i-1}P\_{continutaion}(w\_i))$$ 

where \\(\Lambda\\) is normalizing constant and 0<d<1. 



