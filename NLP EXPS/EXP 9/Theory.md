# Document Similarity Using Cosine Similarity and TF-IDF

---

## Aim

To preprocess multiple text documents, convert them into TF-IDF vectors, and calculate the similarity between each pair of documents using cosine similarity. Then, identify document pairs that are similar based on a predefined threshold.

---

## Theory

### Cosine Similarity

Cosine similarity is a metric that measures the cosine of the angle between two non-zero vectors in a multi-dimensional space. It quantifies how similar two documents are irrespective of their size, focusing on the orientation (direction) of their vector representations.

- **Range:** -1 to 1  
  - 1 indicates identical vectors (documents).  
  - 0 indicates orthogonal (unrelated) vectors.  
  - Values closer to 1 mean higher similarity.

The formula for cosine similarity between two vectors **A** and **B** is:

\[
\text{CosineSimilarity}(\mathbf{A}, \mathbf{B}) = \frac{\mathbf{A} \cdot \mathbf{B}}{\|\mathbf{A}\| \times \|\mathbf{B}\|}
\]

Where:  
- \(\mathbf{A} \cdot \mathbf{B}\) is the dot product of vectors A and B.  
- \(\|\mathbf{A}\|\) and \(\|\mathbf{B}\|\) are the Euclidean norms (lengths) of vectors A and B respectively.

### TF-IDF Vectorization

TF-IDF (Term Frequency-Inverse Document Frequency) is a weighting technique used to reflect the importance of a word to a document relative to a collection of documents (corpus). It helps highlight important terms while down-weighting common words.

---

## Procedure / Steps

1. **Input Documents**:  
   Enter multiple text documents.

2. **Preprocessing**:  
   - Convert text to lowercase.  
   - Remove punctuation.  
   - Tokenize text into words.  
   - Remove stopwords (common words like “is”, “the”).  
   - Apply stemming to reduce words to their root form.

3. **TF-IDF Vectorization**:  
   Convert the preprocessed documents into TF-IDF vectors, each representing the importance of terms within the document relative to the corpus.

4. **Calculate Cosine Similarity**:  
   Compute cosine similarity scores between each pair of document vectors using the formula:

   \[
   \text{CosineSimilarity}(\mathbf{A}, \mathbf{B}) = \frac{\sum_i A_i B_i}{\sqrt{\sum_i A_i^2} \times \sqrt{\sum_i B_i^2}}
   \]

5. **Identify Similar Documents**:  
   Compare the cosine similarity scores against a predefined threshold (e.g., 0.4) and print document pairs exceeding this threshold.

---

## Example with Given Inputs

- **Input Documents:**  
  1. "THIS IS MY FIRST REPORT"  
  2. "THIS IS MY SECOND REPORT"  
  3. "THIS IS MY THIRD REPORT"

- **After Preprocessing:**  
  1. "first report"  
  2. "second report"  
  3. "third report"

- **Vector Representation (Simplified):**

  | Term   | Doc 1 | Doc 2 | Doc 3 |
  |--------|-------|-------|-------|
  | first  | 0.8   | 0     | 0     |
  | report | 0.6   | 0.6   | 0.6   |
  | second | 0     | 0.8   | 0     |
  | third  | 0     | 0     | 0.8   |

- **Cosine Similarity between Doc 1 and Doc 2:**

  \[
  \mathbf{A} = [0.8, 0.6, 0, 0], \quad \mathbf{B} = [0, 0.6, 0.8, 0]
  \]

  - Dot product:

  \[
  0.8 \times 0 + 0.6 \times 0.6 + 0 \times 0.8 + 0 \times 0 = 0.36
  \]

  - Norms:

  \[
  \|\mathbf{A}\| = 1, \quad \|\mathbf{B}\| = 1
  \]

  - Cosine similarity:

  \[
  \frac{0.36}{1 \times 1} = 0.36
  \]

- **Interpretation:**  
  Similarity is low (~0.26 to 0.36 depending on exact TF-IDF values) because only the word “report” is common across documents.

---

## Conclusion

The code successfully:

- Preprocesses multiple documents by cleaning, removing stopwords, and stemming.  
- Converts documents into TF-IDF vectors reflecting term importance.  
- Calculates cosine similarity between every document pair to measure similarity.  
- Identifies similar documents based on a threshold.

In the given example, no document pairs crossed the similarity threshold of 0.4 due to limited word overlap, illustrating how cosine similarity captures meaningful text similarity based on term usage rather than document length.

---


