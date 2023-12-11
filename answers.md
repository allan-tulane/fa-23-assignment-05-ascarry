# CMPS 2200 Assignment 5
## Answers

**Name:**___Abby Scarry___

- **1a.**
  The maximum depth of a d-ary heap is the ceiling of log_d n.


- **1b.**
  The delete-min operation has a work of O(dlog_dn) since d comparisons per level and the insert operation has a work of O(log_dn) since one comparison per level


- **1c.**
  The new bound is O(∣V∣log_d ∣V∣) + O(∣E∣log_d ∣V∣)

- **1d.**
  Using bound, the value is ∣V∣


- **2a.**
  For k = 0:
  APSP(0, 0, 0) = 0.0
  APSP(0, 1, 0) = -2.0
  APSP(0, 2, 0) = 2.0
  APSP(1, 0, 0) = -2.0
  APSP(1, 1, 0) = 0.0
  APSP(1, 2, 0) = 1.0
  APSP(2, 0, 0) = 2.0
  APSP(2, 1, 0) = 1.0
  APSP(2, 2, 0) = 0.0

  For k = 1:
  APSP(0, 0, 1) = 0.0
  APSP(0, 1, 1) = -2.0
  APSP(0, 2, 1) = -1.0
  APSP(1, 0, 1) = -2.0
  APSP(1, 1, 1) = 0.0
  APSP(1,2, 1) = 1.0
  APSP(2, 0, 1) = -1.0
  APSP(2, 1, 1) = 1.0
  APSP(2, 2, 1) = 0.0

  For k = 2:
  APSP(0, 0, 2) = 0.0
  APSP(0, 1, 2) = -2.0
  APSP(0, 2, 2) = -1.0
  APSP(1, 0, 2) = -2.0
  APSP(1, 1, 2) = 0.0
  APSP(1, 2, 2) = 1.0
  APSP(2, 0, 2) = -1.0
  APSP(2, 1, 2) = 1.0
  APSP(2, 2, 2) = 0.0

- **2b.**
  Yes, APSP(i, j, 1) and APSP(i, j, 2) are identical in the case given because the graph is small and vertex 2 does not give any new, shorter paths that were not already accounted for by vertices 0 and 1.

- **2c.**
 The shortest path cost APSP(i, j, k) is determined by the optimal substructure property: APSP(i, j, k) = min(APSP(i, j, k-1), APSP(i, k, k-1) + APSP(k, j, k-1))

- **2d.**
  When implementing top-down memoization for APSP, each subproblem is computed just one time. There are n  subproblems for each pair of vertices (i, j), and with n^2 vertex pairs, the total number of subproblems is n^3. The work is then O(n^3).

- **2e.**
  The dynamic programming algorithm for APSP has a work complexity of O(n^3). Johnson's algorithm has a work complexity of O(|V|^2 log |V| + |V||E|), which is more efficient in many cases. Johnson's algorithm is more efficient. 


- **3a.**
  A solution to the MST problem is not always a solution to the MMET problem since they both focus on different goals. The MST focuses on minimizing the total weight of all edges in the tree and the MMET focuses on minimizing the maximum weight of any single edge. Sometimed, an MST may have edges with higher weights than in an MMET, because it does not focus on minimizing for maximum edge weight like MMET.

- **3b.**
  To find the next best tree after the optimal MST, we would sort the edges in non-decreasing order and then iteratively add the smallest edge that connects two separate trees, skipping the smallest edge in the original MST. This process continues until all vertices are connected, resulting in the next best spanning tree.

- **3c.**
  The work of the next best tree is O(E log E)
