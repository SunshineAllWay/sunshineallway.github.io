# 《Making Numerical Program Analysis Fast》Review
## Paper Info
Making Numerical Program Analysis Fast
Gagandeep Singh, Markus Puschel, Martin Vechev
## Main Work
1. Proposed a method to make numerical program analysis fast
2. Designed an efficient and flexible data structure to represent the abstract domain
3. Octagon can be represented by a matrix form, and all operations in abstract interpretation can be implemented by the operations on the matrix.

In the traditional abstract interpretation, our data structure need to support the following operations:
1. meet
2. join
3. widening
4. Top
5. closure
In this paper, the matrix representation of octagon is straightforward and powerful. Operations including meet, join and Top can be implemented easily in this form. And widening can be implemented by the widening operation in the single matrix unit pointwise.
Because the matrix representation can be computed to the most standard form, in which no other constraints can be concluded from others, we need to compute the closure of a matrix. The algorithm of this part is inspired by the Dijkstra algorithm in the shortest path problem.

In the above five operations, meet, join and widening have the same time complexity, which is O(n2)。The closure operation has a O(n3) time complexity. In order to decrease the time complexity of these operation, some tricks are proposed.

Notice that the matrix are mostly sparse, so meet, join and widening can be done in a shorter time if a spare representation of matrix is applied in the computation.
Moreover, the variables in the octagon can be decomposed into different disjoint parts, and in this way matrix can be decomposed into several submatrixes. Hence the total closure operation can be done in a shorter time.

The time complexity of these operations is summarized in the paper.

## Future work
This work is based on a numerical computation library APRON, and all of algorithms are implemented in this lib. 
However, this work is aimed at the computation of octagon, and the matrix representation is restricted by this domain, which means that polyhedra can not be represented by this form.