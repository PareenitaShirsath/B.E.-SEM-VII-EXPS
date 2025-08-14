# Part-of-Speech (POS) Tagging: Theory, Implementation, and Conclusion

## 🔍 Introduction

Part-of-Speech (POS) tagging is the process of assigning a part of speech (e.g., noun, verb, adjective) to each word in a sentence. This is a fundamental task in Natural Language Processing (NLP) used in applications like information extraction, machine translation, and question answering.

---

## 🧠 POS Tagging: Theory

### What is POS Tagging?
POS tagging is the process of marking up a word in a text as corresponding to a particular part of speech, based on both its definition and its context.

### Common POS Tags
- **NN**: Noun
- **VB**: Verb
- **JJ**: Adjective
- **RB**: Adverb
- **PRP**: Personal pronoun
- **IN**: Preposition
- **DT**: Determiner

### Types of POS Taggers

1. **Rule-Based POS Tagger**  
   - Uses hand-written rules.
   - E.g., Eric Brill’s tagger (Brill Tagger).
   - Pros: Simple, interpretable.
   - Cons: Inflexible to new language usage.

2. **Statistical POS Tagger**  
   - Uses probability and machine learning models.
   - E.g., Hidden Markov Models (HMM).
   - Pros: More adaptable.
   - Cons: Requires training data.

3. **Transformation-Based Tagger**  
   - Hybrid of rule-based and statistical methods.
   - Learns rules automatically from tagged corpora.

4. **Neural POS Tagger**  
   - Based on deep learning (RNNs, LSTMs, BERT).
   - E.g., spaCy, Flair, AllenNLP.
   - Pros: High accuracy.
   - Cons: Computationally expensive.

---

## 🛠 POS Tagging on Sample Text

**Text:**  
> "The quick brown fox jumps over the lazy dog."

### Using NLTK (Rule/Statistical Hybrid)

```python
import nltk
nltk.download('punkt')
nltk.download('averaged_perceptron_tagger')

text = "The quick brown fox jumps over the lazy dog."
tokens = nltk.word_tokenize(text)
pos_tags = nltk.pos_tag(tokens)

print(pos_tags)
