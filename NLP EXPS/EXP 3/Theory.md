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

**Implementation in NLTK:**

```python
from nltk.corpus import stopwords
nltk.download('stopwords')

stop_words = set(stopwords.words('english'))
filtered_tokens = [word for word in tokens if word.lower() not in stop_words]

