# Experiment – Finding Similar Items using Euclidean Distance  

## Aim  
To implement a program that finds similar items based on **Euclidean distance** and visualizes their relationships using a scatter plot.  

---

## Theory  

### Euclidean Distance  
Euclidean distance is the most commonly used measure of similarity (or dissimilarity) between two points in a multidimensional space.  
It represents the **straight-line distance** between two points.  

For two points:  
- \( P = (x_1, y_1, ..., n_1) \)  
- \( Q = (x_2, y_2, ..., n_2) \)  

The Euclidean distance is given by:  

\[
d(P, Q) = \sqrt{(x_1 - x_2)^2 + (y_1 - y_2)^2 + \dots + (n_1 - n_2)^2}
\]  

In 2D, it simplifies to:  

\[
d(P, Q) = \sqrt{(x_1 - x_2)^2 + (y_1 - y_2)^2}
\]  

---

### Properties of Euclidean Distance  
- **Non-Negativity**: Distance is always greater than or equal to zero.  
- **Identity**: Distance between two identical points is zero.  
- **Symmetry**: Distance from \(P\) to \(Q\) is the same as from \(Q\) to \(P\).  
- **Triangle Inequality**: Distance between two points is less than or equal to the sum of distances through a third point.  

---

### Advantages of Euclidean Distance  
- Simple and easy to compute.  
- Intuitive geometric interpretation (straight-line distance).  
- Works well with continuous and normalized data.  

---

### Disadvantages of Euclidean Distance  
- Sensitive to scale: features with larger ranges dominate distance calculation.  
- Not suitable for categorical variables.  
- Can be misleading in high-dimensional spaces due to the **curse of dimensionality**.  
- Sensitive to noise and outliers.  

---

### Use Cases of Euclidean Distance  
- **Clustering Algorithms**: Used in K-means clustering to assign points to the nearest centroid.  
- **Classification**: Basis of K-Nearest Neighbors (KNN) algorithm.  
- **Image Processing**: Comparing pixel intensities or feature vectors.  
- **Recommendation Systems**: Measuring similarity between user profiles or items.  
- **Geographical Mapping**: Measuring distances between locations based on coordinates.  

---

## Conclusion  
Euclidean distance is a fundamental metric for measuring similarity in data analysis and machine learning.  
Although it has limitations (e.g., sensitivity to scale and high dimensions), it remains highly effective for low-dimensional, normalized datasets.  
By applying it to state coordinates, the program demonstrates how similar regions can be identified and visualized.  

