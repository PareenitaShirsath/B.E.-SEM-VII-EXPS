# Text Preprocessing: Tokenization, Filtration, and Script Validation

## Aim
To apply various text preprocessing techniques such as tokenization, filtration of stopwords and punctuation, and script validation on a given dataset to prepare the text data for further Natural Language Processing (NLP) tasks.

## Theory

### 1. Text Preprocessing
Text preprocessing is a foundational step in the NLP pipeline that prepares raw text data for machine learning models or other analysis. Raw text from sources like social media, emails, or SMS messages often contains inconsistencies such as varied capitalization, misspellings, punctuation, and irrelevant words. These irregularities can reduce the quality of the data and negatively affect model performance.

Preprocessing cleans and standardizes the text, reducing noise and focusing on meaningful content. This typically involves multiple steps including tokenization, normalization (like converting to lowercase), removal of stopwords and punctuation, and filtering by script or language. Effective preprocessing can improve the accuracy, efficiency, and robustness of downstream NLP tasks such as classification, sentiment analysis, and topic modeling.

---

### 2. Tokenization
Tokenization is the process of breaking down a piece of text into smaller components called tokens. These tokens are typically words, but can also include phrases, numbers, or punctuation depending on the use case.

This step is important because it converts unstructured text into a structured sequence that algorithms can process. Tokenization allows each token to be analyzed independently or in context with others.

For example, the sentence:

*"Hello world! Welcome to NLP."*

would be tokenized into:

`["Hello", "world", "!", "Welcome", "to", "NLP", "."]`

Tokenization must carefully handle edge cases such as contractions ("don't" → ["do", "n't"]), hyphenated words ("well-known"), and punctuation marks to maintain the semantic integrity of the text.

---

### 3. Filtration
Filtration removes tokens that provide little or no useful information for the intended NLP task. The two main categories filtered are:

- **Stopwords:** These are common words that occur frequently in text but typically do not carry strong meaning or contribute to the main content. Examples include "is," "the," "and," "in." Removing stopwords reduces dimensionality and computational cost while retaining the important keywords.

- **Punctuation:** Symbols like commas, periods, exclamation points, and question marks are often removed since they generally do not affect the semantic meaning in many analyses. However, punctuation can be important in some tasks like sentiment analysis or syntax parsing, so removal depends on the use case.

Filtering is commonly performed by comparing tokens to predefined stopword lists and removing punctuation characters using string libraries or regular expressions. This step helps in focusing on meaningful content and improving the signal-to-noise ratio in the dataset.

---

### 4. Script Validation
Script validation is the process of verifying that tokens belong to a desired writing system or character set. This is important when processing multilingual data or text that may contain emojis, special symbols, or foreign scripts.

For many English-centric NLP applications, restricting tokens to the **Latin script** (ASCII characters) is useful to remove extraneous or noisy tokens such as:

- Emojis: 😀, ❤️, 🎉
- Non-Latin alphabets: Cyrillic, Arabic, Chinese characters
- Special symbols or control characters

This validation is usually implemented using regular expressions or Unicode script checks to retain only tokens matching the targeted script. Script validation ensures cleaner and more consistent input data, which can improve the accuracy of models that are trained only on a specific language or character set.

---

## Summary of Applied Techniques
- **Dataset Used:** SMS Spam Collection Dataset from UCI Machine Learning Repository.
- **Steps Implemented:** 
  1. Download and load dataset.
  2. Tokenize messages into words.
  3. Remove stopwords and punctuation.
  4. Retain only tokens with Latin characters (ASCII).
- **Purpose:** Clean and normalize text to improve performance in downstream tasks such as classification.

---

## References
- UCI Machine Learning Repository: [SMS Spam Collection Dataset](https://archive.ics.uci.edu/ml/datasets/SMS+Spam+Collection)
- Bird, Klein, & Loper, *Natural Language Processing with Python*, O'Reilly Media, 2009.
- NLTK Documentation: https://www.nltk.org/

