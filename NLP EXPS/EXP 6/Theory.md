# Part-of-Speech (POS) Tagging: Theory, Implementation, and Conclusion

## 🔍 Introduction

Part-of-Speech (POS) tagging is the process of assigning a part of speech (e.g., noun, verb, adjective) to each word in a sentence. This is a fundamental task in Natural Language Processing (NLP) used in applications like information extraction, machine translation, and question answering.

---

## 🧠 POS Tagging: Theory

# Part-of-Speech (POS) Tagging

## 🎯 Aim:
To study the different POS taggers and perform POS tagging on the given text.

---

## 📚 Theory

Part-of-Speech (POS) Tagging is the process of assigning a part-of-speech label (noun, verb, adjective, etc.) to each word in a sentence. It plays a crucial role in various NLP applications like syntactic parsing, information retrieval, and machine translation.

### 🔹 POS Tagging Overview
- Tagging is a form of classification where a descriptor (tag) is assigned to each token.
- POS tags include Noun, Verb, Adjective, Adverb, Pronoun, Preposition, Conjunction, etc.
- POS tagging can be done using:
  - Rule-based methods
  - Stochastic (Statistical) methods
  - Transformation-based methods

---

### 🔸 1. Rule-Based POS Tagging

**Definition:**  
Rule-based POS tagging uses dictionaries and hand-written rules to assign correct tags to words.

**How it Works:**
- **Stage 1**: Assigns a list of potential tags to each word using a dictionary (lexicon).
- **Stage 2**: Applies hand-crafted rules to resolve ambiguity and assign the most appropriate tag.

**Types of Rules:**
- Context-pattern rules
- Regular expressions compiled into finite-state automata

**Properties:**
- Knowledge-driven
- Manual rule creation (~1000 rules)
- Explicit language modeling and smoothing
- Rules based on linguistic context (e.g., articles preceding nouns)

---

### 🔸 2. Stochastic POS Tagging

**Definition:**  
Uses statistical models to predict the most probable POS tag based on training data.

**Approaches:**
1. **Word Frequency Approach**:
   - Tags assigned based on the most frequent tag observed for the word in a training corpus.
   - May result in invalid tag sequences.

2. **Tag Sequence Probabilities (n-gram models)**:
   - Considers the probability of a tag given the previous n tags.
   - Most common: bigram or trigram models.

**Properties:**
- Probability-based tagging
- Requires a labeled training corpus
- Cannot handle out-of-vocabulary (OOV) words well
- Separate testing and training datasets required
- Simple implementation using frequency-based decisions

---

### 🔸 3. Transformation-Based Tagging (Brill Tagging)

**Definition:**  
A hybrid technique that combines rule-based and statistical methods. Uses Transformation-Based Learning (TBL) to learn tagging rules from data.

**How it Works:**
- Initially assigns baseline tags (e.g., most frequent tag).
- Applies transformation rules iteratively to correct mistakes.
- Rules are automatically learned from the training corpus.

**Inspired by:**
- **Rule-based**: Uses readable, hand-crafted-style rules
- **Statistical**: Rules are learned from data using machine learning

**Properties:**
- Rule templates are used to generate rules.
- High accuracy and interpretable model.
- Adapts well to real-world linguistic patterns.

---

## ✅ Summary of POS Tagging Methods

| Tagger Type           | Approach        | Needs Training? | Handles Ambiguity | Learnable Rules | Accuracy |
|-----------------------|------------------|------------------|--------------------|------------------|----------|
| Rule-Based            | Manual Rules      | ❌               | ✔️                 | ❌               | Medium   |
| Stochastic            | Statistical       | ✔️               | ✔️ (via probabilities) | ❌         | High     |
| Transformation-Based  | Hybrid (ML + Rules) | ✔️             | ✔️                 | ✔️               | Very High|

---
