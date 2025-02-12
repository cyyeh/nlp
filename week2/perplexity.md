# Perplexity Computation

This is an optional reading about perplexity computation to make sure you remember the material of the videos and you are in a good shape for the quiz of this week.

Perplexity is a popular quality measure of language models. We can calculate it using the formula:

$$
\mathcal{P}=p\left(w_{\text {test}}\right)^{-\frac{1}{N}}, \text { where } p\left(w_{\text {test}}\right)=\prod_{i=1}^{N+1} p\left(w_{i} | w_{i-n+1}^{i-1}\right)
$$
​	 

Recall that all words of the corpus are concatenated and indexed in the range from 1 to NN. So NN here is the length of the test corpus. Also recall that the tokens out of the range are fake start/end tokens to make the model correct.

Check yourself: how many start and end tokens do we have in a trigram model?

Now, if just one probability in the formula above is equal to zero, the whole probability of the test corpus is zero as well, so the perplexity is infinite. To avoid this problem, we can use different methods of smoothing. One of them is Laplacian smoothing (add-1 smoothing), which estimates probabilities with the formula:

$$
p\left(w_{i} | w_{i-n+1}^{i-1}\right)=\frac{c\left(w_{i-n+1}^{i}\right)+1}{c\left(w_{i-n+1}^{i-1}\right)+V}
$$

Note, that V here is the number of possible continuations of the sequence $w_{i-n+1}^{i-1}$
​	 , so V is the number of unique unigrams in the train corpus plus 1. Do you see why? Well, we include the fake end token to this number, because the model tries to predict it each time, just us as any other word. And we do not include the start tokens, because they serve only as a prefix for the first probabilities.

Now, let’s review the following task together.

Task:

Apply add-one smoothing to the trigram language model trained on the sentence:

“This is the cat that killed the rat that ate the malt that lay in the house that Jack built.”

Find the perplexity of this smoothed model on the test sentence:

“This is the house that Jack built.”

Solution:

We have n=3, so we will add two start tokens <s1>, <s2> and one end token <end>.

Note, that we add (n-1) start tokens, since the start tokens are needed to condition the probability of the first word on them. The role of the end token is different and we always add just one end token. It's needed to be able to finish the sentence in the generative process at some point.

So, what we have is:

train: <s1> <s2> This is the cat that killed the rat that ate the malt that lay in the house that Jack built <end>

test: <s1> <s2> This is the house that Jack built <end>

Number of unique unigrams in train is 14, so V = 14 + 1 = 15.

Number of words in the test sentence is 7, so N = 7.

=p(wtest)−1N, where p(wtest)=∏i=18p(wi|wi−2wi−1)=∏i=18c(wi−2wi−1wi)+1c(wi−2wi−1)+15
All right, now we need to compute 8 conditional probabilities. We can do it straightforwardly or notice a few things to make our life easier.

First, note that all bigrams from the test sentence occur in the train sentence exactly once, which means we have (1 + 15) in all denominators.

Also note, that "is the house" is the only trigram from the test sentence that is not present in the train sentence. The corresponding probability is p(house | is the) = (0 + 1) / (1 + 15) = 0.0625.

All other trigrams from the test sentence occur in the train sentence exactly once. So their conditional probabilities will be equal to (1 + 1) / (1 + 15) = 0.125.

In this way, perplexity is (0.0625 * 0.125 ^ 7) ^ (-1/7) = 11.89.

The quiz of this week might seem to involve heavy computations, but actually it does not, if you think a bit more :) Good luck!

