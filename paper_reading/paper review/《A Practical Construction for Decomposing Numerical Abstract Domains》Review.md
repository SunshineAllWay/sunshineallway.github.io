# 《A Practical Construction for Decomposing Numerical Abstract Domains》Review
## Paper Info
A Practical Construction for Decomposing Numerical Abstract Domains
Gagandeep Singh, Markus Puschel, Martin Vechev
## Main work
In this paper, a general method of decomposing numerical abstract domains is proposed. We only need to consider the following five kinds of operations.
- Conditional operation
- Assignment
- Meet
- Join
- Widening
If we process these operations in the decomposed form of numerical abstract domains, the time complexity can be cut down to a low level. In the paper, Table 2 and Table 5 summarize the time complexity of these operations on polyhedra and octagon.
## Some details
Conditional operation and assignment are easy to handle. We only need to assure the partition permissible. Some simple union or negate of set are enough to handle these two operations.
Meet and join are also not difficult to process. Join is a bit hard to handle, because a refinement operation is needed in the join operation.
Widening operation is the most complex operation among these five. I didn't read deeply in this section.
## Some Remarks
- The work has been implemented in the project ELINA
- Some other acceleration tricks are proposed in other works, including reinforcement learning.
- The method in this paper is general. When designing different numerical abstract domain, some specific tricks can be used to make the calculation faster.

