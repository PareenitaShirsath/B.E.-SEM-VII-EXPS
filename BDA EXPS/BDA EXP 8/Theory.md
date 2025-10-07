# 🧮 Flajolet–Martin Algorithm (FM Algorithm)

## 🎯 Aim
To implement the **Flajolet–Martin Algorithm**, a probabilistic approach used in **Big Data** to **estimate the number of distinct elements** (cardinality) in a data stream using very little memory.

---

## 📘 Introduction

In large-scale data processing (e.g., social media feeds, network packets, or log streams), it’s impractical to store and count every unique item directly due to **memory and time constraints**.  
The **Flajolet–Martin (FM) Algorithm** provides an **approximate** but **highly efficient** way to estimate the **count of distinct elements** in a data stream.

---

## 🧠 Basic Idea

The algorithm is based on **hashing** and **probability**.

1. Each incoming element is **hashed** into a binary value using a uniform hash function.
2. The algorithm counts the number of **trailing zeros** in the binary representation of the hash.
3. The **maximum number of trailing zeros** observed among all elements gives an indication of how many distinct elements are present.

Intuition:
- If many distinct elements exist, the hash outputs will have more variation.
- The probability of seeing a hash ending in `k` zeros is roughly `1 / 2^k`.
- Therefore, if the **maximum trailing zeros count = R**, we can estimate:
  
  \[
  \text{Number of distinct elements} \approx 2^R
  \]

---

## ⚙️ Steps in the Algorithm

1. **Initialize:**  
   Choose multiple hash functions \( h_1, h_2, ..., h_m \).

2. **Hash Each Element:**  
   For each element in the stream:
   - Compute \( h_i(x) \) for each hash function.
   - Convert the hash value to binary form.
   - Count the number of **trailing zeros**.

3. **Track Maximum Zeros:**  
   For each hash function \( h_i \), record the **maximum number of trailing zeros** seen across all elements.

4. **Estimate Cardinality:**  
   For each hash function, compute \( 2^{R_i} \), where \( R_i \) is the maximum number of trailing zeros for that hash function.

5. **Aggregate Estimates:**  
   Take the **average** (or **median**) of all estimates to reduce variance.

---

## 🧩 Example

Consider a small data stream:  
`[a, b, c, a, d, e, f, g, h, i]`

Let’s say we use 5 hash functions and observe trailing zeros as follows:

| Hash Function | Max Trailing Zeros (R) | 2^R |
|----------------|------------------------|------|
| h1 | 1 | 2 |
| h2 | 2 | 4 |
| h3 | 0 | 1 |
| h4 | 2 | 4 |
| h5 | 0 | 1 |

**Average Estimate:**

\[
\frac{2 + 4 + 1 + 4 + 1}{5} = 2.4
\]

So, the **estimated number of distinct elements ≈ 2.4**

---

## 🧮 Mathematical Background

If elements are hashed uniformly, the probability that a random hash value ends with at least `r` zeros is:

\[
P(\text{at least } r \text{ zeros}) = \frac{1}{2^r}
\]

Hence, the **expected value of maximum trailing zeros (R)** grows with the **logarithm of the number of distinct elements (n)**:

\[
E[R] \approx \log_2(n)
\]

Thus, an estimate for \( n \) is:

\[
n \approx 2^R
\]

To improve accuracy, multiple hash functions are used, and the **average of estimates** provides a better approximation.

---

## 💡 Advantages

- **Memory Efficient:** Uses logarithmic memory (O(log n))
- **Fast:** Processes each element in constant time O(1)
- **Scalable:** Suitable for large-scale or streaming data
- **Simple:** Easy to implement and extend

---

## ⚠️ Limitations

- Provides only an **approximate count**, not exact.
- **Hash collisions** or poor hash functions can reduce accuracy.
- Requires multiple hash functions to reduce variance.

---

## 🚀 Applications

- Big Data stream processing systems (e.g., Spark Streaming, Flink)
- Network traffic analysis
- Counting unique users, IPs, or search queries
- Duplicate detection and distinct counting in databases

---

## 🧾 Conclusion

The **Flajolet–Martin Algorithm** is a foundational technique in **streaming data analytics**, offering an efficient way to estimate distinct counts using minimal space.  
It paved the way for more advanced algorithms like **LogLog** and **HyperLogLog**, which are widely used in modern Big Data systems.

---

## 📜 References

- Flajolet, P., & Martin, G. N. (1985). *Probabilistic counting algorithms for data base applications*. Journal of Computer and System Sciences, 31(2), 182–209.  
- "Mining of Massive Datasets" — Jure Leskovec, Anand Rajaraman, Jeffrey Ullman.

---
