1. Consider using this encoder decoder model for machine translation
![[Pasted image 20240817074432.png]]
Ture/False: This model is a "conditional language model" in the sense that the decoder portion (shown in purple) is modeling the probability of the output sense $y$ given the input  sentence $x$
- [ ] False
- [ ] True

2.  In beam search, if you increase the beam with **B**, which of the following would you expect to be true?
- [ ] Beam search will converge after fewer steps
- [ ] Beam search will generally find better solutions (i.e. do a better job maximizing $P(y|x)$)
- [ ] Beam search will run more slowly
- [ ] Beam search will use up more memory

3. True/False: In machine translation, if we carry out beam search without using sentence normalization, the algorithm will tend to output overly long translations.
- [ ] True
- [ ] False

4. Suppose you are building a speech recognition system, which uses an RNN model to map from audio clip $x$ to a text transcript $y$. Your algorithm uses beam search to try to find the value of $y$ that maximizes $P(y|x)$.
   On a dev set example, given an input audio clip, your algorithm outputs the transcript $\hat{y}$ = "I'm building an A Eye system in Silly con Valley.", whereas a human gives a much superior transcript $y*$ = "I'm building an AI system in Silicon Valley"
   According to your model,
   $P(\hat{y}|x) = 1.09 * 10^{-7}$
   $$
   
