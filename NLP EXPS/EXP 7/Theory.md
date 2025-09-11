# Part-of-Speech Tagging and Chunking Analysis

## Aim
The primary aim of this exercise is to explore and understand the grammatical structure of English sentences by performing part-of-speech (POS) tagging and chunking on a rich text corpus. Specifically, we intend to:

- Assign the correct grammatical categories (noun, verb, adjective, etc.) to each word in a given paragraph.
- Identify and extract meaningful phrases such as noun phrases (NP) and verb phrases (VP) through chunking.
- Analyze how varying the size of the training corpus impacts the performance and accuracy of chunking.
- Gain insights into the syntactic and semantic roles of words and phrases in natural language processing (NLP).

## Theory

### Part-of-Speech (POS) Tagging
POS tagging is a crucial step in natural language processing that involves labeling each word in a sentence with its corresponding grammatical category. These categories include:

- **Nouns (NN, NNS):** Represent people, places, things, or ideas (e.g., *boy*, *dogs*).
- **Verbs (VB, VBD, VBG, VBN, VBP, VBZ):** Indicate actions, states, or occurrences (e.g., *run*, *ran*, *running*).
- **Adjectives (JJ):** Describe or modify nouns (e.g., *young*, *narrow*).
- **Adverbs (RB):** Modify verbs, adjectives, or other adverbs, indicating manner, degree, frequency, etc. (e.g., *quickly*, *beautifully*).
- **Pronouns (PRP):** Substitute for nouns (e.g., *he*, *it*).
- **Prepositions (IN):** Indicate relationships between nouns or pronouns and other words (e.g., *through*, *with*).
- **Determiners (DT):** Introduce nouns (e.g., *the*, *a*).
- **Conjunctions (CC):** Connect words or clauses (e.g., *and*, *but*).
- **Interjections (UH):** Express emotion or hesitation (e.g., *Wow!*).

By tagging words accurately, computational models gain a better understanding of sentence structure, which is essential for further language processing tasks.

### Chunking (Shallow Parsing)
Chunking groups POS-tagged words into higher-level phrases or chunks. The most common chunks are:

- **Noun Phrases (NP):** Groups of words functioning as a noun unit, usually including a determiner, adjectives, and a noun (e.g., *the young boy*, *a narrow alley*).
- **Verb Phrases (VP):** Groups centered on a verb and possibly including its objects or complements (e.g., *had been searching*, *leaped into his arms*).
- **Prepositional Phrases (PP):** Groups beginning with a preposition and followed by a noun phrase (e.g., *through the alley*).

Unlike full parsing, chunking does not specify hierarchical structure but identifies flat, non-overlapping phrases that act as building blocks for sentence meaning.

### Importance of Training Size
The accuracy of chunking and POS tagging can depend heavily on the amount and quality of training data available. Larger corpora provide:

- **Better coverage** of diverse sentence structures.
- **More examples** to learn complex grammar patterns.
- **Reduced overfitting** and improved generalization.

In this exercise, although we used a small corpus, we simulated the effect of increasing training size by incrementally processing more sentences to observe how chunk detection improves with corpus size.

## Conclusion
Through POS tagging, we successfully identified the grammatical role of each word in the paragraph, demonstrating the variety of word classes present in natural language. The tagging included nouns, verbs in different tenses, adjectives, adverbs, conjunctions, prepositions, and interjections, showcasing the rich linguistic structure of the text.

Subsequent chunking allowed us to extract noun phrases and verb phrases, which are critical in understanding sentence meaning and structure. Our simulation of varying training sizes revealed that as more data becomes available, chunking systems can detect more phrases, leading to improved parsing quality.

This exercise underscores the fundamental role of POS tagging and chunking in NLP applications such as information extraction, machine translation, sentiment analysis, and question answering. Moreover, it highlights that both the quality of features (correct grammatical labels) and the quantity of training data significantly impact the performance of language models.

For future work, expanding the corpus and using machine learning-based chunkers could yield more robust results, especially for complex sentences and ambiguous constructions.

---

### References
- Jurafsky, D., & Martin, J. H. (2020). *Speech and Language Processing* (3rd ed.). Draft.
- Bird, S., Klein, E., & Loper, E. (2009). *Natural Language Processing with Python*. O'Reilly Media.
- NLTK Documentation: https://www.nltk.org/


