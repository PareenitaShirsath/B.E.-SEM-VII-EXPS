# **Experiment No. 8: Clustering (K-Means / CURE)**

**Date:** 10/8/2025  
**Subject:** Big Data Analytics  

---

## **Aim**
To study and understand the **CURE (Clustering Using REpresentatives)** algorithm and compare it with traditional K-Means clustering.

---

## **Theory**

Clustering is an **unsupervised machine learning** technique used to group similar data points into clusters based on their similarity or distance.  
Two major clustering approaches are **K-Means** and **CURE**.

---

### **1. K-Means Clustering**
- K-Means is a **centroid-based** algorithm that partitions data into **K clusters**.
- Each cluster is represented by its **mean (centroid)**.
- The algorithm iteratively assigns points to the nearest centroid and updates centroids until convergence.
- It is simple and efficient but **fails with irregular cluster shapes or outliers**.

---

### **2. CURE Algorithm (Clustering Using Representatives)**

CURE is an advanced **hierarchical clustering algorithm** designed to handle:
- Non-spherical clusters  
- Varying cluster sizes  
- Noise and outliers  

#### **Key Concepts:**
1. Each cluster is represented by a **fixed number of representative points** rather than a single centroid.
2. These representative points are **shrunk toward the cluster centroid** by a constant factor (shrinkage factor α).
3. **Clusters are merged** based on the **minimum distance between their representative points**.
4. CURE can be combined with **random sampling and partitioning** to efficiently handle very large datasets.

---

## **Algorithm Steps**
1. Select a random sample of data points.  
2. Partition the data into smaller subsets and partially cluster them.  
3. Select a fixed number of representative points from each cluster.  
4. Shrink the representative points toward the centroid by a constant factor.  
5. Merge clusters based on the **closest pair of representative points**.  
6. Repeat until the required number of clusters is achieved.

---

## **Example Summary**

For three clusters (Cluster 1, Cluster 2, Cluster 3), representative points are selected from each.  
Distances between these representative points are calculated, and the two clusters with the **minimum representative distance** are merged.  
Example result:


---

## **Advantages of CURE**
1. Handles **non-spherical and complex-shaped clusters** effectively.  
2. Works well with **datasets containing outliers**.  
3. **Scalable** for large datasets using random sampling.  
4. Provides **better accuracy** than centroid-based clustering (like K-Means).  
5. Robust against noise and cluster size variations.  

---

## **Disadvantages of CURE**
1. **Computationally expensive** compared to K-Means.  
2. Requires **tuning parameters** like number of representatives and shrinkage factor.  
3. **Higher memory usage** for large numbers of representative points.  
4. Performance depends on **sample selection** and initialization.  
5. Difficult to interpret for very high-dimensional data.  

---

## **Conclusion**
The **CURE algorithm** improves upon traditional K-Means by using multiple representative points instead of a single centroid.  
It produces more **accurate and robust clusters** for complex datasets, making it highly suitable for **real-world big data clustering applications**.

---

