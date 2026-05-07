---
title: Text-Based Data for Financial Forecasting
subject: Quantitative Methods
tags: [CFA-L2, quantitative-methods, big-data, text-analytics, machine-learning]
aliases: [Text wrangling, Text feature engineering, Bag of words, Document term matrix, NLP for finance, Sentiment analysis]
---

# Text-Based Data for Financial Forecasting

## The Real-World Analogy

Text data is like raw ore. Earnings call transcripts, news articles, 10-K filings, and social media posts may contain valuable signals, but a machine learning model cannot use paragraphs directly. The analyst has to refine the ore: clean the text, split it into useful pieces, preserve important context, and turn it into a numeric matrix.

Only after that can a model learn whether words, phrases, tone, or entities help forecast returns, defaults, earnings surprises, or volatility.

## The Big Idea

Text-based financial forecasting converts unstructured language into structured variables.

```text
Raw text
  |
  v
Clean text
  |
  v
Tokens and normalized words
  |
  v
Features such as n-grams, sentiment, entities
  |
  v
Document-term matrix
  |
  v
Machine learning model
```

## Text Preparation

Raw text usually contains formatting and noise:

| Raw issue | Typical treatment |
|---|---|
| HTML tags | Remove |
| Extra whitespace | Normalize |
| Upper/lowercase variation | Lowercase |
| Punctuation | Usually remove or replace |
| Financial symbols | Preserve with tags when meaningful |
| Numbers | Often replace with a generic number token |

In finance, do not blindly delete every symbol. A percent sign, dollar sign, or number may carry useful meaning. Replacing "$5 million" with `/money/ /number/ million` may preserve structure better than deleting it.

## Tokenization

[[Tokenization]] splits text into units called tokens.

Sentence:

```text
Revenue growth slowed sharply.
```

Tokens:

```text
revenue | growth | slowed | sharply
```

Tokens are the basic features from which text models are built.

## Stop Words

Stop words are extremely common words such as:

```text
the, is, a, and, of
```

They often add little predictive value and create a larger, noisier feature matrix. Removing them can improve model efficiency.

The exam trap is that not all common words are useless in every context. In sentiment analysis, negation words such as "not" can be very important.

## Stemming Versus Lemmatization

Both methods reduce related word forms to a common base.

| Method | What it does | Example | Tradeoff |
|---|---|---|---|
| Stemming | Chops words using rules | analyzing -> analyz | Faster, rougher, may create non-words |
| Lemmatization | Converts to true linguistic root | analyzing -> analyze | More accurate, more computationally expensive |

Stemming reduces data size but can make tokens less interpretable. Lemmatization preserves more linguistic meaning.

## N-Grams

An n-gram treats a sequence of words as one token.

| N-gram | Example |
|---|---|
| Unigram | good |
| Bigram | not_good |
| Trigram | better_than_expected |

N-grams are important because word order can change meaning. "Good" and "not good" should not be treated as the same signal.

## Named Entity Recognition

[[Named entity recognition]] identifies tokens as specific entity types:

| Text | Entity tag |
|---|---|
| Apple | Organization |
| Tim Cook | Person |
| Seoul | Location |
| $5 billion | Money |

NER helps the model distinguish proper nouns and financial entities from ordinary vocabulary.

## Bag-Of-Words And Document-Term Matrix

A [[Bag of words]] is the vocabulary list of retained tokens. A [[Document-term matrix]] turns documents into rows and tokens into columns.

| Document | growth | default | downgrade |
|---|---:|---:|---:|
| Doc 1 | 2 | 0 | 0 |
| Doc 2 | 0 | 1 | 1 |
| Doc 3 | 1 | 0 | 1 |

The cell value may be a raw count, a frequency, or a weighting such as TF-IDF.

## TF-IDF

Term frequency-inverse document frequency gives higher weight to terms that are common in a specific document but not common across all documents.

Term frequency:

$$
TF=\frac{\text{count of token in document}}{\text{total tokens in document}}
$$

Document frequency:

$$
DF=\frac{\text{documents containing token}}{\text{total documents}}
$$

Inverse document frequency:

$$
IDF=\ln\left(\frac{1}{DF}\right)
$$

TF-IDF:

$$
TFIDF=TF \times IDF
$$

## Worked Numerical Example

Suppose the token "growth" appears 2 times in a 20-word sentence. The corpus has 1,000 sentences, and "growth" appears in 50 of them.

Term frequency:

$$
TF=\frac{2}{20}=0.10
$$

Document frequency:

$$
DF=\frac{50}{1000}=0.05
$$

Inverse document frequency:

$$
IDF=\ln\left(\frac{1}{0.05}\right)=\ln(20)=2.9957
$$

TF-IDF:

$$
TFIDF=0.10(2.9957)=0.2996
$$

This value becomes the document-term matrix entry for "growth" in that sentence. The term is meaningful because it appears often in the sentence but not in most documents.

## Sentiment Features

Financial text models often classify text as positive, negative, or neutral. A model might learn that terms such as "beat expectations" and "margin expansion" are positive, while "default risk" and "going concern" are negative.

The output can be:

| Output | Example |
|---|---|
| Classification | positive or negative |
| Probability | 72% probability of positive sentiment |
| Score | sentiment from -1 to +1 |

The sentiment feature can then be used in a return, earnings, default, or volatility model.

## Interpretation and Exam Traps

| Trap | What goes wrong | Exam-day fix |
|---|---|---|
| Most frequent words are most useful | Stop words dominate but add little signal | Remove or downweight low-information words |
| Rarest words are always best | Very rare terms can overfit | Useful tokens often have intermediate frequency |
| Deleting all numbers and symbols | Loses financial meaning | Replace key numbers/symbols with tags |
| Confusing stemming and lemmatization | Treats both as equally precise | Lemmatization returns true roots; stemming is rougher |
| Ignoring word order | Misses phrases like "not good" | Use n-grams when sequence matters |

## Memory Hooks

**Text must become a matrix before a model can learn from it.**

**Tokenize, normalize, engineer, then model.**

**In finance, numbers and symbols often deserve tags, not deletion.**

## Related Concepts

- [[Big Data Projects]]
- [[Logistic Regression]]
- [[Support Vector Machines]]
- [[Classification and Regression Trees (CART)]]
- [[Confusion Matrix]]
- [[Dummy Variables and Qualitative Independent Variables]]
- [[Machine Learning]]
