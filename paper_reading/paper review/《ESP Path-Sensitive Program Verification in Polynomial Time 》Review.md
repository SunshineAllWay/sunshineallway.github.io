# 《ESP: Path-Sensitive Program Verification in Polynomial Time 》Review
## Paper Info
ESP: Path-Sensitive Program Verification in Polynomial Time
Manuvir Das, Sorin Lerner, Mark Seigle

## Major Contribution
The authors present a new algorithm for partial program verfication that can run in polynomial time and space. Previous work on partial verification has only focused on path-sensitive analysis methods, which limits the applicability to large programs.

The authors propose "property simulation" based on the heuristic that a branch is likely to be relevant only if the property FSM transitions to different states along the arms of the branch. This method avoids exponential blowup and only captures relevant branching behavior. This is the major contribution of this research paper, and the core insight and algorithm make this work state of art.

## Main Work
The authors present property analysis, a general framework for tracking property states and execution states using path-sensitive dataflow analysis. The framework consists of two parts: intra-procedural property analysis and inter-procedural property analysis.

### Intra-procedural property analysis
The intra-procedural property analysis in this paper is based on the traditional waiting-list algorithm in the dataflow analysis.

![1](D:\HKUST\论文笔记\Pic\5.JPG)    ![2](D:\HKUST\论文笔记\Pic\6.JPG)

The above algorithm is similar to the traditional data-flow framework. In this paper, the authors assume that each merge point only has two predecessors, and each branch point only has two successors. Hence, in the above algorithm, we only need to process two nodes when we encounter the merge points or branch points.

Based on the intra-procedural property analysis framework, a framework for property simulation can be easily implemented by chosing different domain of execution states and the join operations. In this paper, the authors propose three different kinds of frameworks, including the fully path-sensitive analysis, standard dataflow analysis and property simulation. Some examples are explained in the paper, and the details of these three frameworks are fully illustrated.

### Inter-procedural property analysis
The inter-procedural property analysis is a extension of the intra-procedural version through the use of partial transfer functions or function summary edges. The algorithm framework is following.

![3](D:\HKUST\论文笔记\Pic\7.JPG)

As shown above, the inter-procedural property analysis  merges the information in the function summary edges at the function call sites. The main part is similiar to the intra-procedural version.

In the evaluation section, the authors conduct some experiments on the gcc source code, and analyze the validity of the usage of some file operations. The results demonstrate that property simulation has a good performance both in the precision and efficiency.

## Future Work
Some further exploration can be conducted in the future. Although the frameworks proposed in this paper has a good scalability, the parallel algorithm has not been desiged in this work. There are many phases which can be implemented in a parallel form, such as VFG construction and interface expression computation.
Meanwhile, some infeasible paths can be filtered when we encounter a branch node. Some methods in the Pinpoint paper can be referred and applied to this work.
