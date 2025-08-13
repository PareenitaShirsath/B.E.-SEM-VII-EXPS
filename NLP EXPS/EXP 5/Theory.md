# Implementation of N-Gram Model Using a Dataset

## Aim
To implement an **N-Gram language model** using a dataset of sentences stored in a CSV file, and use it to predict the next word in a sequence based on the context.

---

## Theory

An **N-Gram model** is a probabilistic language model that predicts the next word in a sequence by considering the previous **N-1** words (context).  
It is based on the **Markov assumption**, which simplifies the prediction problem by assuming that the future word depends only on a limited history of past words, not the entire sentence.

### Key Concepts

- **N-Gram**: A sequence of N consecutive words.
  - **Unigram (N=1)**: "The", "dog", "barks"
  - **Bigram (N=2)**: "The dog", "dog barks"
  - **Trigram (N=3)**: "The dog barks"
- **Context**: The previous N-1 words used to predict the next word.
- **Probability Formula**:  
  For a bigram model (N=2):  
  \[
  P(w_n | w_{n-1}) = \frac{\text{Count}(w_{n-1}, w_n)}{\text{Count}(w_{n-1})}
  \]
- **Steps to Build an N-Gram Model**:
  1. Load sentences from a dataset.
  2. Tokenize text (remove punctuation and split into words).
  3. Count occurrences of word sequences of length N.
  4. Calculate probabilities and store in a dictionary.
  5. Use the model to predict the most likely next word given a context.

### Applications
- Text prediction in mobile keyboards
- Autocomplete in search engines
- Spelling correction
- Speech recognition
- Machine translation

### Advantages
- Simple and interpretable
- Fast to implement for small datasets

### Limitations
- Poor handling of unseen word combinations (**zero-frequency problem**)
- Requires large storage for high N
- Ignores long-distance dependencies

---

## Conclusion
The N-Gram model provides a simple yet effective approach to text prediction by learning from frequency patterns in a dataset.  
By using a CSV dataset of sentences, we can build a statistical model that predicts the most probable next word for a given context.  
Although it is easy to implement and works well for basic language tasks, it struggles with unseen sequences and cannot capture long-range dependencies.  
For more complex applications, advanced models like Recurrent Neural Networks (RNNs) or Transformers can be used.

