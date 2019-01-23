# textnoiz
Brief literature review on handling noisy text input from ASR.


**Bibliography**

A few relevant papers are presented below:

### [(2018) INVESTIGATING THE EFFECTS OF WORD SUBSTITUTION ERRORS ON SENTENCE EMBEDDINGS](https://arxiv.org/pdf/1811.07021.pdf)

#### Notes

In this paper, they propose a way of *simulating* realistic ASR transcription errors and evaluate the resultant embeddings on the semantic textual similarity task. 
They observe that the nature of word subst. error in ASR depends 1) on the *phonemic*  2) on the *semantic* distance between true word and substituted word.
    
They try to find the most robust to ASR error sentence embeddings. The most **robust** encoder is *InferSent*, which relies on a **transfer learning** approach: the encoder is trained with a bi-LSTM NN on SNLI (Stanford Natural Language Inference) dataset. The embeddings show the best results in textual similarity.

---


### [(2018) Training and Prediction Data Discrepancies: Challenges of Text Classification with Noisy, Historical Data](https://arxiv.org/pdf/1809.04019.pdf)

#### Notes

More experimental / mini-survey paper. Authors investigate the effect of different types of noise in prediction accuracy for 3 datasets. BOW SVM, NBOW SVM and CNN classifiers are used. Results are encouraging, as introduced noise does not significantly affect classification accuracy. Related work is informing as it supports the robustness to noise with previous work. 

Caveats:

- Sample size in tokens is a bit large (82-221 tokens)  
- No sequential classifier explored (LSTM). Does noise lead to error accumulation?  
- Only synthetic noise was explored. What happens when errors are accumulated in ASR output LM?  

---

### [(2018) Learning from Past Mistakes: Improving Automatic Speech Recognition Output via Noisy-Clean Phrase Context Modeling](https://arxiv.org/pdf/1802.02607.pdf)

#### Notes

Authors propose an ASR post-processing system to improve ASR output. They model ASR as a noisy channel and recover from mistakes using a probabilistic model based on context of past errors. Paper is well-written as they clearly state their hypotheses and provide a decent experimental section. 

--- 

### [(2018) Unsupervised Transfer Learning for Spoken Language Understanding in Intelligent Agents](https://arxiv.org/pdf/1811.05370.pdf)

#### Notes

ELMo embeddings are proposed to encode raw ASR data:
- ELMo embeddings for unsupervised knowledge transfer from raw ASR text--> SLU accuracy gains.
- ELMo-Light (ELMoL), a **light-weight ELMo alternative** that is well-suited for commercial settings.

(they train an LM network consisting of character level CNNs and a single bi-LSTM layer on unlabeled
ASR text to compute contextual word representation. Contrary to ELMo, they do not freeze the lower bi-LSTM layer. 
To avoid catastrophic forgetting (forgetting prior knowledge), they use gradual unfreezing, discriminative fine-tuning       and slanted triangular learning rates, inspired by ULMFiT.)

- They combine unsupervised and supervised transfer learning --> **additive effect** of the two techniques.

--- 

### [(2018) ROBUST SPOKEN LANGUAGE UNDERSTANDING WITH UNSUPERVISED ASR-ERROR ADAPTATION](https://speechlab.sjtu.edu.cn/papers/sz128-zhu-icassp18.pdf)

#### Notes

Authors propose an unsupervised model for domain adaptation on ASR errors. Model is based on Bidirectional Language modeling and improves upon (un-adapted) baseline and seq2seq based adaptation.


---

### [(2018) Hybrid Attention based Multimodal Network for Spoken Language Classification](http://www.aclweb.org/anthology/C18-1201)

#### Notes

The authors demonstrate the benefits of including textual information to improve performance on spoken language classification tasks.
They propose a multimodal network, that takes as input the audio signal and text from utterance-level speech data and applies both feature-level and modality-level attention an their representations.
The inputs are encoded seperately using RNNs with attention and then weighted with modality specific scores.


---

### [(2017) ASR error management for improving spoken language understanding](https://arxiv.org/pdf/1705.09515.pdf)

#### Notes

The author proposes using ASR confidence measures as additional input features to the sequence encoder.
At each timestep the word embedding of the current word is concatenated with the ASR confidence measures and other semantically relevant features such as word embeddings of its neighbors, the length of the current word, part of speech (POS) tags, syntactic dependency labels.
They use two ASR confidence measures: the ASR word posterior probability and the MS-MLP (Multi-Stream Multi-Layer Perceptron) confidence measure. The MS-MLP is a network trained to compute scores for Correct and Error labels of ASR generated hypotheses. 


### [(2018) Spoken SQuAD: A Study of Mitigating the Impact of Speech Recognition Errors on Listening Comprehension](https://arxiv.org/pdf/1804.00320.pdf)

#### Notes

The authors of this paper use phoneme sequences for words motivated by the observation that even when ASR system predicts a wrong word, subword units may be correct. They propose the Phoneme-CNN, which is similar to a character level CNN, but applies convolutional filters to the phoneme embeddings to extract a word-level representation.

---
