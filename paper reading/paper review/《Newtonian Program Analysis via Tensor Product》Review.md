# 《Newtonian Program Analysis via Tensor Product》Review

  ## Paper Info

  《Newtonian Program Analysis via Tensor Product》 POPL 2016
  
  Thomas Reps, Emma Turetsky, and Prathmesh Prabhu

  ## Major Contributions

  This paper presents a technique for solving the LCFL sub-problems produced during successive rounds of Newton's method, which can be applied in predicate abstraction. The authors transform each LCFL problem into a left linear problem, which is a regular system of equations over a different semiring. The solution of the original LCFL system can be obtained based on the solution of the regular system of equations. This is the core insight of their work

  The main contributions of this paper include:

  - An approach to transform an LCFL problem into a left linear problem is proposed, and the solution of the original LCFL problem can be obtained based on the solution of the left linear problem.
  - Newtonian Program Analysis via Tensor Product (NPA-TP) is presented and can improve the traditional Newton's method for solving the LCFL problems.
  - The authors describe a new way to handle loops and local variables by NPA-TP.

  This paper is the first work which uses regularizing transformation in NPA. The most important result is a method to transform an LCFL equation system over semiring S into a left-linear, and hence a regular system of equations over a tensor-product semiring. They show that there are non-commutative semirings for which they can apply a transform with no loss of precision.

  ## Main Work

  The authors give a new way to solve the LCFL system equations, which is a traditional form of dataflow framework. The goal of this work is to speed up the Newtonian Program Analysis of interprocedural programs. Moreover, they construct the equivalent interprocedural programs for loops to handle loop structures. Local functions are also handled by the merge functions.

  Based on the theory of formal language, a regular language is a subset of LCFL and is equivalent to the left linear CFL or the right linear CFL. They notice that regular language has good property in the NPA, which can reduce the cost of time. Hence they try to convert the LCFL system equations to the RL system equations.

  The transformation is not simple. In Section 3, they give an example of transformation, which causes the loss of precision, that means the solution of the original LCFL system obtained from the solution of RL system is not the least solution. Hence they propose a regularizing transformation with no loss in Section 4 based on tensor-product. The transformation preserves all of the necessary properties, which assure that the solution of the original problem is the least solution. At the last part of this paper, the authors handle some complex program structures, including loops and the functions with local variables, in order to make their approach more practical.

  To sum up, this work is a brand-new work on the interprocedural program analysis. The insight is elegant and innovative.

  ## Some Criticism

  This work provides a new view to obtain the solution of LCFL system equations. The methods in this work are fantastic and rigorous. However, the experimental results show that this work still has the following limitations.

  - As the authors showed, this work is not practical enough. The original goal of this work is to speed up the Newtonian program analysis, which is achieved. But their method cannot contribute much to NPA, and NPA-TP is still slower than EWPDS. The results show that EWPDS is the algorithm of choice for predicate-abstraction problems.
  - The applications of NPA-TP should be illustrated in details. In this work, they choose predicate abstraction as an application of their methods. However, the details of predicate abstraction are not enough in this paper. Moreover, some more specific applications should be discussed in the paper to demonstrate the value of this work in practical use.
