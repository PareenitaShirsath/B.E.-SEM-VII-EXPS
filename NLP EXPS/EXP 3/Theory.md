# NLP Experiment No. 3: Text Preprocessing Techniques

**Name:** Pareenita A. Shirsath  
**B.E. AI & DS Roll No:** 57  
**PRN:** 221101062

---

## 🎯 Aim

To apply and understand various text preprocessing techniques—**Stop Word Removal**, **Lemmatization**, and **Stemming**—using the Natural Language Toolkit (NLTK) in Python, and to observe their effects on multilingual text data.

---

## 📘 Theory

### 1. Stop Word Removal

**Definition:**  
Stop words are common words (e.g., "the", "is", "in") that carry little meaningful information and are often removed during text preprocessing to reduce noise and improve the efficiency of NLP models.

**Why Remove Stop Words?**

- **Reduces Noise:** Eliminates words that don't contribute significant meaning.
- **Improves Efficiency:** Reduces the size of the dataset, leading to faster processing.
- **Enhances Model Performance:** Helps models focus on more meaningful words.

## 2. Lemmatization

**Definition:**  
Lemmatization is the process of reducing a word to its base or dictionary form, known as a lemma. Unlike stemming, lemmatization considers the word's meaning and part of speech, ensuring that the base form is a valid word.

**Why Use Lemmatization?**

- **Improves Accuracy:** Ensures words with similar meanings are treated as the same.
- **Reduces Data Redundancy:** By reducing words to their base forms, it reduces redundancy in the dataset.
- **Enhances Model Performance:** Helps models understand the context and meaning of words.

**Implementation in NLTK:**

## 2. Lemmatization

**Definition:**  
Lemmatization is the process of reducing a word to its base or dictionary form, known as a lemma. Unlike stemming, lemmatization considers the word's meaning and part of speech, ensuring that the base form is a valid word.

**Why Use Lemmatization?**

- **Improves Accuracy:** Ensures words with similar meanings are treated as the same.
- **Reduces Data Redundancy:** By reducing words to their base forms, it reduces redundancy in the dataset.
- **Enhances Model Performance:** Helps models understand the context and meaning of words.

  ## 3. Stemming

**Definition:**  
Stemming is a text preprocessing technique in Natural Language Processing (NLP) that reduces words to their root form by removing prefixes and suffixes. This process standardizes words, which helps improve the efficiency and effectiveness of various NLP tasks.

**Why Use Stemming?**

- **Speeds Up Processing:** Stemming is faster than lemmatization because it uses simple, rule-based approaches without considering the context of the word.
- **Reduces Data Size:** Helps in reducing the number of unique words, making the dataset more manageable.
- **Simplifies Analysis:** Useful in applications like search engines and information retrieval systems where exact word forms are less important.

## 4. Lemmatization

**Definition:**  
Lemmatization is the process of reducing a word to its base or dictionary form, known as a lemma. Unlike stemming, lemmatization considers the word's meaning and part of speech, ensuring that the base form is a valid word.

**Why Use Lemmatization?**

- **Improves Accuracy:** Ensures words with similar meanings are treated as the same. For example, "running" and "ran" are both reduced to "run," preserving their semantic meaning. :contentReference[oaicite:0]{index=0}

- **Reduces Data Redundancy:** By reducing words to their base forms, it reduces redundancy in the dataset. This leads to smaller datasets, making it easier to handle and process large amounts of text for analysis or training machine learning models. :contentReference[oaicite:1]{index=1}

- **Enhances Model Performance:** Helps models understand the context and meaning of words. By treating all similar words as the same, it improves the performance of NLP models by making text more consistent. :contentReference[oaicite:2]{index=2}

