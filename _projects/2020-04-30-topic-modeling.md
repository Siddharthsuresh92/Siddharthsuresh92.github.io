---
title:  "Movie recommendation system using Topic Modeling"
---

## Introduction
Natural language processing is something I find fascinating and a technique that exists in that realm is called Topic Modeling. Topic modeling is an unsupervised learning approach that essentially tries to assign topics to documents.

Before jumping in, let me provide a background on the terms that will be used in this post. Say we have a collection of texts in the form of movie reviews, the entire collection is called a 'corpus'. This corpus is futher made up of individual reviews or 'documents'. Each such document has one or more sentences which is a collection of words. Now that you know what 'corpus' and 'document' stand for, let's move on to Topic Modeling itself.

## Topic Modelling
Topic modeling using Latent Dirichlet Allocation (LDA) works by assigning topics to each document. LDA uses the premise that each topic is a just a distribution of words and each document is a distribution of topics. For example, a corpus of news articles could have topics such as 'sports', 'politics', 'business' etc. and each of those topics could have a distribution of words. The topic 'sports' could have words like football, athlete, basketball in its distribution while the topic 'politics' could have words like prime minister, president, policy.

The reason this method is termed unsupervised is because there's no way to know for sure how many topics really exist. For say movie reviews, if the reviews were only for Sci-fi movies, essentially a single topic is enough, but if one chooses 5 topics the algorithm would try to find words for topics such that the corpus can be split into 5 different groups. You can think of K-means but for texts. Topic Modeling essentially tries to cluster texts together.

Given that we already have words to process in the form of a corpus, the algorithm's job is to:
1. find topics for each word in a document so that it can learn the distrbution of words for each topic
2. find the distribution of topics for each document given the words in that document.

![image-center]({{ site.url }}{{ site.baseurl }}/assets/images/LDA.png){: .align-centre} 


