# textnoiz
Brief lit review on handling noisy text input


**Bibliography**

A few relevant papers are presented below:

### [(2018) INVESTIGATING THE EFFECTS OF WORD SUBSTITUTION ERRORS ON SENTENCE EMBEDDINGS](https://arxiv.org/pdf/1811.07021.pdf)

#### Notes

In this paper, they propose a way of *simulating* realistic ASR transcription errors and evaluate the resultant embeddings on the semantic textual similarity task. 
They observe that the nature of word subst. error in ASR depends 1) on the *phonemic*  2) on the *semantic* distance between true word and substituted word.
    
They try to find the most robust to ASR error sentence embeddings. The most **robust** encoder is *InferSent*, which relies on a **transfer learning** approach: the encoder is trained with a bi-LSTM NN on SNLI (Stanford Natural Language Inference) dataset. The embeddings show the best results in textual similarity.

---

https://arxiv.org/pdf/1802.08395.pdf

---


### [(2018) Training and Prediction Data Discrepancies: Challenges of Text Classification with Noisy, Historical Data](https://arxiv.org/pdf/1809.04019.pdf)

#### Notes

More experimental / mini-survey paper. Authors investigate the effect of different types of noise in prediction accuracy for 3 datasets. BOW SVM, NBOW SVM and CNN classifiers are used. Results are encouraging, as introduced noise does not significantly affect classification accuracy. Related work is informing as it supports the robustness to noise with previous work. 

Caveats:

- Sample size in tokens is a bit large (82-221 tokens)  
- No sequential classifier explored (LSTM). Does noise lead to error accumulation?  
- Only synthetic noise was explored. What happens when errors are accumulated in ASR output LM?  

### [(2018) Hybrid Attention based Multimodal Network for Spoken Language Classification](http://www.aclweb.org/anthology/C18-1201)


