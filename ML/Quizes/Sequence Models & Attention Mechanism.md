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
   $P(y*|x) = 7.21 * 10^{-8}$
   Would you expect increasing the beam width B to help correct this example?
   
- [ ] No, because $P(y*|x)  \leq P(\hat{y}|x)$ indicates the error should be attributed to the RNN rather than to search the algorithm 

5. Continuing the example from Q4, suppose you work on your algorithm for a few more weeks, and now find that for the vast majority of examples on which your algorithm makes a mistake, $P(y*|x) > P(\hat{y}|x)$. This suggest you should not focus your attention on improving the search algorithm
- [ ] False
- [ ] True

6. Consider the attention model for the machine translation
   ![[Pasted image 20240817081241.png]]
   Further, here is the formula for $\alpha ^{<t,t'>}$
   ![[Pasted image 20240817081411.png]]
   Which of the following statements about $\alpha ^{<t, t'>}$ are trrue?
   - [ ] We expect $\alpha^{<t, t'>}$ to generally larger for values of $\alpha^{<t'>}$ that are highly relevant to the value the network should output for $y ^{<t>}$ **Note the indices in the superscripts**
   - [ ] $\sum_{t'}\alpha^{<t, t'>} = 1$ **Note the summation is over $t'$**

 7. The network learns where to "pay attention" by learning the values $e^{<t, t'>}$, which are computed using a small neural network:
 8. 