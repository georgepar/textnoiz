# textnoiz
Brief lit review on handling noisy text input


**Bibliography**

A few relevant papers are presented below:

## [(2018) INVESTIGATING THE EFFECTS OF WORD SUBSTITUTION ERRORS ON SENTENCE EMBEDDINGS](https://arxiv.org/pdf/1811.07021.pdf)

### Notes

In this paper, they propose a way of *simulating* realistic ASR transcription errors and evaluate the resultant embeddings on the semantic textual similarity task. 
They observe that the nature of word subst. error in ASR depends 1) on the *phonemic*  2) on the *semantic* distance between true word and substituted word.
    
They try to find the most robust to ASR error sentence embeddings. The most **robust** encoder is *InferSent*, which relies on a **transfer learning** approach: the encoder is trained with a bi-LSTM NN on SNLI (Stanford Natural Language Inference) dataset. The embeddings show the best results in textual similarity.

---

https://arxiv.org/pdf/1802.08395.pdf
