# NLTK Tutorial

## Install

```text
>>> import nltk
>>> nltk.download()
```

## Tokenizer

### punkt

This tokenizer divides a text into a list of sentences, by using an unsupervised algorithm to build a model for abbreviation words, collocations, and words that start sentences. It must be trained on a large collection of plaintext in the target language before it can be used.

The NLTK data package includes a pre-trained Punkt tokenizer for English.

## CorpusReader

Available corpus readers see [link](https://www.nltk.org/howto/corpus.html).

### PlaintextCorpusReader

```python
import nltk

nltk.download('punkt')

from nltk.corpus.reader.plaintext import PlaintextCorpusReader

corpus = PlaintextCorpusReader(...)

raw = corpus.raw()

paras = corpus.paras()

sents = corpus.sents()

words = corpus.words()

```

## Analysis

```python
word_freq_dist = nltk.FreqDist(corpus.words())

# topk
word_freq_dist.most_common(10)

# Frequency for a word
word_freq_dist.get('data')

```





## References

1. [Code comment: nltk punkt](https://www.nltk.org/_modules/nltk/tokenize/punkt.html)

