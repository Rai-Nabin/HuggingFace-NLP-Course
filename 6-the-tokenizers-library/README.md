# Introduction
When fine-tuning a model for a specific task, the same pretrained tokenizer is commonly used. However, when training a model from scratch, using a tokenizer pretrained on a different domain or language is usually suboptimal. For instance, a tokenizer trained on English may not perform well on Japanese texts due to notable differences in spaces and punctuation usage between the two languages.

In this chapter, the focus is on training a new tokenizer for a corpus of texts so it can be used to pretrain a language model. This will all be done with the help of the [🤗 Tokenizers](https://github.com/huggingface/tokenizers) library, which provides the “fast” tokenizers in the [🤗 Transformers](https://github.com/huggingface/transformers) library.

**Topics covered:**
- How to train a new tokenizer similar to the one used by a given checkpoint on a new corpus of texts
- The special features of fast tokenizers
- The differences between the three main subword tokenization algorithms used in NLP today
- How to build a tokenizer from scratch with the 🤗 Tokenizers library and train it on some data
# Training a new tokenizer from an old one
If a language model is not available in the language you are interested in, or if your corpus is very different from the one your language model was trained on, you will most likely want to retrain the model from scratch using a tokenizer adapted to your data. That will require training a new tokenizer on your dataset. 

> Training a tokenizer is not the same as training a model! Model training uses stochastic gradient descent to make the loss a little bit smaller for each batch. It’s randomized by nature (meaning you have to set some seeds to get the same results when doing the same training twice). Training a tokenizer is a statistical process that tries to identify which subwords are the best to pick for a given corpus, and the exact rules used to pick them depend on the tokenization algorithm. It’s deterministic, meaning you always get the same results when training with the same algorithm on the same corpus.

Please refer to this [**notebook**](./notebook/1-training_a_new_tokenizer.ipynb).

