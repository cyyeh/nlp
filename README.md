# Natural Language Processing

## Overview

This course covers a wide range of tasks in Natural Language Processing from basic to advanced: sentiment analysis, summarization, dialogue state tracking, to name a few. Upon completing, you will be able to recognize NLP tasks in your day-to-day work, propose approaches, and judge what techniques are likely to work well.  The final project is devoted to one of the most hot topics in today’s NLP. You will build your own conversational chat-bot that will assist with search on StackOverflow website. The project will be based on practical assignments of the course, that will give you hands-on experience with such tasks as text classification, named entities recognition, and duplicates detection. 

Throughout the lectures, we will aim at finding a balance between traditional and deep learning techniques in NLP and cover them in parallel. For example, we will discuss word alignment models in machine translation and see how similar it is to attention mechanism in encoder-decoder neural networks. Core techniques are not treated as black boxes. On the contrary, you will get in-depth understanding of what’s happening inside. To succeed in that, we expect your familiarity with the basics of linear algebra and probability theory, machine learning setup, and deep neural networks. Some materials are based on one-month-old papers and introduce you to the very state-of-the-art in NLP research.

## Key Concepts by Week

Week 1, Intro and text classification
> In this module we will have two parts: first, a broad overview of NLP area and our course goals, and second, a text classification task. It is probably the most popular task that you would deal with in real life. It could be news flows classification, sentiment analysis, spam filtering, etc. You will learn how to go from raw texts to predicted classes both with traditional methods (e.g. linear classifiers) and deep learning techniques (e.g. Convolutional Neural Nets).

- Identify traditional pipeline for text preprocessing and classification
- Build a model that predicts tags on StackOverflow
- Apply deep learning techniques to text classification

---

Week 2, Language modeling and sequence tagging
> In this module we will treat texts as sequences of words. You will learn how to predict next words given some previous words. This task is called language modeling and it is used for suggests in search, machine translation, chat-bots, etc. Also you will learn how to predict a sequence of tags for a sequence of words. It could be used to determine part-of-speech tags, named entities or any other tags, e.g. ORIG and DEST in "flights from Moscow to Zurich" query. We will cover methods based on probabilistic graphical models and deep learning.

- Build LSTM model for named entities recognition
- Distinguish n-gram and RNN language models
- Give examples of smoothing techniques in language modeling
- Propose and compare approaches for sequence tagging tasks

--- 

Week 3, Vector Space Models of Semantics
> This module is devoted to a higher abstraction for texts: we will learn vectors that represent meanings. First, we will discuss traditional models of distributional semantics. They are based on a very intuitive idea: "you shall know the word by the company it keeps". Second, we will cover modern tools for word and sentence embeddings, such as word2vec, FastText, StarSpace, etc. Finally, we will discuss how to embed the whole documents with topic models and how these models can be used for search and data exploration.

- Interpret word2vec and other word embedding techniques
- Build a ranking system based on sentence embeddings
- Summarize applications of topic modeling
- Describe how to train a topic model only from texts

---

Week 4, Sequence to sequence tasks
> Nearly any task in NLP can be formulates as a sequence to sequence task: machine translation, summarization, question answering, and many more. In this module we will learn a general encoder-decoder-attention architecture that can be used to solve them. We will cover machine translation in more details and you will see how attention technique resembles word alignment task in traditional pipeline.

- Recognize sequence to sequence tasks in NLP and judge on appropriate architectures
- Describe traditional pipeline in machine translation
- Train seq2seq neural networks for applied tasks
- Explain attention mechanism in neural networks

---

Week 5, Dialog systems
> This week we will overview so-called task-oriented dialog systems like Apple Siri or Amazon Alexa. We will look in details at main building blocks of such systems namely Natural Language Understanding (NLU) and Dialog Manager (DM). We hope this week will encourage you to build your own dialog system as a final project!

- Develop a chat-bot that answers intended questions and holds a conversation
- Understand the architecture of task-oriented dialog systems
- Understand how NLU and DM can be implemented
- Understand how neural networks can help to train better NLU and DM