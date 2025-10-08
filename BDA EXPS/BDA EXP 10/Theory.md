🧪 BDA EXPERIMENT NO: 10

Name: Pareenita A. Shirsath
Roll No: 57
Branch: B.E. A.I. & D.S.

✅ Aim

To implement the PageRank algorithm using MapReduce-like logic in Python and compute the rank of web pages based on their link structure.

📚 Theory

PageRank is an algorithm developed by Larry Page and Sergey Brin (the founders of Google) that ranks web pages based on their importance. It is used by search engines to prioritize the order of search results.

The PageRank value of a page reflects the probability that a "random surfer" will land on that page by randomly following links. Pages with more incoming links from important pages are ranked higher.

Formula:
𝑃
𝑅
(
𝐴
)
=
1
−
𝑑
𝑁
+
𝑑
∑
𝑖
=
1
𝑛
𝑃
𝑅
(
𝐼
𝑖
)
𝐿
(
𝐼
𝑖
)
PR(A)=
N
1−d
	​

+d
i=1
∑
n
	​

L(I
i
	​

)
PR(I
i
	​

)
	​


Where:

𝑃
𝑅
(
𝐴
)
PR(A): PageRank of page A

𝑑
d: Damping factor (typically 0.85)

𝑁
N: Total number of pages

𝐼
𝑖
I
i
	​

: Pages linking to page A

𝐿
(
𝐼
𝑖
)
L(I
i
	​

): Number of outbound links from page 
𝐼
𝑖
I
i
	​


🔁 Code Execution Flow

Graph defined as a dictionary where keys are pages and values are lists of outgoing links.

Initial PageRank is set equally among all pages.

Mapper emits contributions from a page to its linked pages.

Reducer sums up contributions to each page.

Damping factor is applied to simulate the "random surfer" behavior.

Iteration is repeated for a fixed number of times (10 in this case).
✅ Advantages of PageRank

Simple and efficient to implement.

Takes the importance of incoming links into account.

Works well for identifying authoritative pages.

Resilient to minor manipulations in the link structure.

❌ Disadvantages of PageRank

Doesn't consider the content of the page, only the link structure.

Can be manipulated by link farms or spammy backlinking.

Not real-time; recalculation is required for updated ranks.

Doesn't account for context or relevance to search queries.

🧩 Conclusion

PageRank is a foundational algorithm in web search engines that provides a reliable metric for ranking web pages. Despite its limitations, it introduces a powerful idea of link-based importance. In this experiment, we successfully implemented PageRank using a simplified MapReduce approach in Python and observed the computed importance of each node after multiple iterations.

