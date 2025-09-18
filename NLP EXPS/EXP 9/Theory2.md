What is Cosine Similarity?

Cosine similarity is a metric used to measure how similar two vectors are irrespective of their magnitude (length). It measures the cosine of the angle between two vectors in a multi-dimensional space.

Range: The cosine similarity value ranges from -1 to 1.

1 means vectors are identical (point in the same direction).

0 means vectors are orthogonal (completely unrelated).

-1 means vectors point in opposite directions.

Since TF-IDF vectors have non-negative values, cosine similarity values will range from 0 to 1 in this context.

Formula for Cosine Similarity between vectors A and B:
CosineSimilarity
(
𝐴
,
𝐵
)
=
𝐴
⋅
𝐵
∥
𝐴
∥
×
∥
𝐵
∥
CosineSimilarity(A,B)=
∥A∥×∥B∥
A⋅B
	​


Where:

𝐴
⋅
𝐵
A⋅B is the dot product of vectors A and B.

∥
𝐴
∥
∥A∥ is the Euclidean norm (length) of vector A.

∥
𝐵
∥
∥B∥ is the Euclidean norm (length) of vector B.

Step-by-Step Explanation Using Your Code and Input
Step 1: Input Documents

You enter 3 documents:

Doc 1: "THIS IS MY FIRST REPORT"

Doc 2: "THIS IS MY SECOND REPORT"

Doc 3: "THIS IS MY THIRD REPORT"

Step 2: Preprocessing

Each document is preprocessed using these sub-steps:

Lowercased: "this is my first report" → "this is my first report" (already lowercase)

Punctuation removed: None here.

Tokenization: Splitting into words.

Stopword Removal: Removes common words like "this", "is", "my".

Stemming: Reduces words to root form (e.g., "running" → "run").

After preprocessing:

Doc 1 → "first report"

Doc 2 → "second report"

Doc 3 → "third report"

Step 3: TF-IDF Vectorization

Each document is converted into a vector based on the TF-IDF scores of the terms in the document collection.

Vocabulary across all docs: ["first", "report", "second", "third"]

Representing each document as a vector of length 4 (each dimension corresponds to one word):

Term	Doc 1	Doc 2	Doc 3
first	tfidf1	0	0
report	tfidf2	tfidf2	tfidf2
second	0	tfidf3	0
third	0	0	tfidf4

TF-IDF values depend on term frequency and inverse document frequency.

Step 4: Vector Representation (Simplified)

Let’s say approximate TF-IDF values for illustration:

For "report": appears in all docs, so lower weight, say 0.6

For unique words "first", "second", "third": appear in one doc only, so higher weight, say 0.8

Vectors:

Doc 1 = [0.8 (first), 0.6 (report), 0, 0]

Doc 2 = [0, 0.6 (report), 0.8 (second), 0]

Doc 3 = [0, 0.6 (report), 0, 0.8 (third)]

Step 5: Calculate Cosine Similarity Between Documents

For example, between Doc 1 and Doc 2:

𝐴
=
[
0.8
,
0.6
,
0
,
0
]
,
𝐵
=
[
0
,
0.6
,
0.8
,
0
]
A=[0.8,0.6,0,0],B=[0,0.6,0.8,0]

Dot product:

𝐴
⋅
𝐵
=
(
0.8
×
0
)
+
(
0.6
×
0.6
)
+
(
0
×
0.8
)
+
(
0
×
0
)
=
0
+
0.36
+
0
+
0
=
0.36
A⋅B=(0.8×0)+(0.6×0.6)+(0×0.8)+(0×0)=0+0.36+0+0=0.36

Norm of A:

∥
𝐴
∥
=
0.8
2
+
0.6
2
+
0
+
0
=
0.64
+
0.36
=
1
=
1
∥A∥=
0.8
2
+0.6
2
+0+0
	​

=
0.64+0.36
	​

=
1
	​

=1

Norm of B:

∥
𝐵
∥
=
0
+
0.6
2
+
0.8
2
+
0
=
0.36
+
0.64
=
1
=
1
∥B∥=
0+0.6
2
+0.8
2
+0
	​

=
0.36+0.64
	​

=
1
	​

=1

Cosine similarity:

0.36
1
×
1
=
0.36
1×1
0.36
	​

=0.36

Your code shows 0.26 instead of 0.36 because actual TF-IDF values vary, but the logic is the same.

Step 6: Result Interpretation

Cosine similarity between Doc 1 and Doc 2 is about 0.26 (low similarity).

Same for Doc 1 & Doc 3, Doc 2 & Doc 3.

This happens because only the word "report" is common; other words differ.

Step 7: Thresholding and Output

You set the similarity threshold at 0.4 to consider documents “similar.” Since all similarities are below 0.4, no document pairs are considered similar.

Summary: What Your Code Does and Why Output Looks This Way
Step	Description	Your Input Example
Input	Reads 3 documents	Doc1: "first report", Doc2: "second report", Doc3: "third report" (after preprocessing)
Preprocessing	Lowercase, remove punctuation, stopwords, stemming	Result: "first report", "second report", "third report"
TF-IDF Vectorization	Converts docs into weighted vectors	Vectors based on unique/common words
Cosine Similarity Calculation	Measures angle between vectors to find similarity	Similarities ~0.26 (low, because only "report" is common)
Thresholding	Prints only pairs with similarity ≥ 0.4	No pairs meet threshold
