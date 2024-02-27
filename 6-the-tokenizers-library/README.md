# Introduction
When fine-tuning a model for a specific task, the same pretrained tokenizer is commonly used. However, when training a model from scratch, using a tokenizer pretrained on a different domain or language is usually suboptimal. For instance, a tokenizer trained on English may not perform well on Japanese texts due to notable differences in spaces and punctuation usage between the two languages.

In this chapter, the focus is on training a new tokenizer for a corpus of texts so it can be used to pretrain a language model. This will all be done with the help of the [🤗 Tokenizers](https://github.com/huggingface/tokenizers) library, which provides the “fast” tokenizers in the [🤗 Transformers](https://github.com/huggingface/transformers) library.

**Topics covered:**
- How to train a new tokenizer similar to the one used by a given checkpoint on a new corpus of texts
- The special features of fast tokenizers
- The differences between the three main subword tokenization algorithms used in NLP today
- How to build a tokenizer from scratch with the 🤗 Tokenizers library and train it on some data