# **Experiment No. 7: DGIM Algorithm**

**Date:** 6/10/2025  
**Subject:** Big Data Analytics  

---

## **Aim**
To implement the **DGIM (Datar–Gionis–Indyk–Motwani)** algorithm to approximate the count of `1`s in the most recent N bits of a binary stream using limited memory.

---

## **Theory**

In streaming data scenarios, it is not feasible to store all incoming bits because of memory limitations.  
The **DGIM Algorithm** provides an efficient way to **estimate the number of 1s** in the last **N bits** of a binary stream while using **O(log² N)** space.

It achieves this by maintaining **buckets**, where:
- Each bucket represents a group of 1s.
- Each bucket has a **timestamp** (for the most recent `1`) and a **size** (number of 1s it represents).
- At most **two buckets** of the same size are allowed.
- When more than two buckets of the same size appear, the **two oldest** are **merged** into one bucket of **double size**.

### **Key Operations**
1. **Add bit:**  
   - When a `1` is seen, a new bucket of size 1 is added.
   - If more than two buckets of the same size exist, merge the two oldest ones.

2. **Expire buckets:**  
   - Remove buckets older than N bits (outside the window).

3. **Query:**  
   - To estimate the number of 1s in the last `k` bits:  
     - Sum the sizes of all buckets completely within the window.  
     - Add **half the size** of the first bucket that only partially overlaps the window.

---

## **Algorithm Steps**

1. Initialize an empty list (deque) of buckets.  
2. For each incoming bit:
   - Increment current time.
   - If bit = 1:
     - Create a new bucket `(timestamp, size=1)`.
     - Merge if more than 2 buckets have the same size.
   - Expire buckets older than `N`.
3. For a query of last `k` bits:
   - Count all buckets with timestamps ≥ current_time - k.
   - For the first bucket that crosses the threshold, add half of its size.
   - Return the estimated count.

---

## **Python Code**

```python
import math
from collections import deque

class DGIM:
    def __init__(self, N):
        self.N = N              # Window size
        self.buckets = deque()  # Each bucket: (timestamp, size)
        self.current_time = 0

    def _expire_buckets(self):
        # Remove buckets outside the window
        while self.buckets and self.buckets[0][0] <= self.current_time - self.N:
            self.buckets.popleft()

    def _merge_buckets(self):
        # Merge buckets with same size if more than 2 exist
        i = len(self.buckets) - 1
        while i >= 2:
            if (len(self.buckets) > i and
                self.buckets[i][1] == self.buckets[i-1][1] == self.buckets[i-2][1]):
                merged_size = self.buckets[i-1][1] * 2
                merged_timestamp = self.buckets[i-1][0]
                del self.buckets[i-2]
                del self.buckets[i-2]  # Shifted after first delete
                self.buckets.insert(i-2, (merged_timestamp, merged_size))
                i = len(self.buckets) - 1
            else:
                i -= 1

    def add_bit(self, bit):
        self.current_time += 1
        self._expire_buckets()
        if bit == 1:
            self.buckets.append((self.current_time, 1))
            self._merge_buckets()

    def query(self, k):
        # Approximate number of 1s in the last k bits
        count = 0
        threshold_time = self.current_time - k
        for i in range(len(self.buckets) - 1, -1, -1):
            timestamp, size = self.buckets[i]
            if timestamp > threshold_time:
                count += size
            else:
                count += size // 2
                break
        return count

# Example usage:
dgim = DGIM(32)  # Window size 32
stream = [1,0,1,1,0,1,0,0,1,1,1,0,1,0,1,0,1,1,0,0,1,1,1,0,0,1,1,0,1,0,0,1]

for bit in stream:
    dgim.add_bit(bit)

print("Approximate count of 1s in last 16 bits:", dgim.query(16))
print("Approximate count of 1s in last 32 bits:", dgim.query(32))

