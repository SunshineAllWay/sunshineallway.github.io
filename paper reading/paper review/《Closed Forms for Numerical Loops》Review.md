# 《Closed Forms for Numerical Loops》Review

## Paper Info

《Closed Forms for Numerical Loops》 POPL 2019
Zachary Kincaid, Jason Breck, John Cyphert, Thomas Reps

## Major Contributions

This work is an interesting work of loop theory in static analysis. The problems including loop terminations and loop invariants are important open problems, and it is always a tough task to handle loops in static analysis. This work proposes a novel and elegant approach to obtain closed forms for numerical loops. This work is in a theoretical style and contains a plenty of mathematical theorems and proofs, which is really my taste.

The main contributions of this paper include: 

- Periodic rational linear loops have closed forms which can be obtained in a polynomial time, and the logic for expressing closed forms is decidable, yielding decision procedures for verifying safety and termination of a class of numerical loops over rational number.
- If one of the eigenvalues of the linear loop is not periodic rational, the loop can be over-approximated and a periodic rational linear loop can maintain some behaviors of it. 
- The logical fragment required to express closed forms of iterated maps with periodic rational eigenvalues is decidable.

The paper is a fundamental work on closed forms for numerical loops, and has a significant meaning for the future work. This work has many broad applications including solving orbit problems, uniform terminations and so on. In a word, this paper is one of my favorite research works I have read these days.

## Main Work
The authors give a closed form for the numerical loops. They starts from a specific kind of loops, which is a periodic rational linear loops. This loop can be modeled as a linear algebra system, and all of its eigenvalues are rational numbers or the n-th roots of rational numbers. This assures that the logical expression about closed forms of loops is decidable. They propose Algorithm 1 to compute a periodic rational spectral decomposition of a matrix in a polytime, yielding the closed forms for the corresponding linear numerical loop from this periodic rational spectral decomposition.

The amazing part of this work is the generalization of periodic rational linear loops. They use this class of loops to approximate the behaviors of general loops. In the section 6, they show Example 6.2 to illustrate their idea. In a general loop without the periodic rational property, the behavior of some valuables in the loop might be lost because of the over approximation. However, their method does work and can provide closed forms of other variables and expressions. In the section 6, they also model the recursive procedures and loop guards, which make their approach more applicable.

At the end of their work, they give a decision procedures for linear loops to find out whether the logical fragment required to express closed forms of iterated maps with periodic rational eigenvalues is decidable. This problem is converted to find the upper bound of the roots of an exponential polynomial. Algorithm 2 uses a linear search to find this upper bound based on some prime mathematical results.

To sum up, this work is more like a mathematical research work. The results in this paper are meaningful and useful in the future research on other field including loop termination, and orbit problems. Because of page limitation, the mathematical details are not summarized in this review, and we only discuss the meaning of main conclusions.

## Some Criticism
This work provides a complete answer about the closed forms for periodic rational linear loops, and a fantastic way to approximate other kinds of linear loops. Nonlinear loops can also be handled in other ways. The paper is well-written in a mathematical style. However, as a paper in computer science, it has serveral limitations and needs to be discussed and improved.

- The authors develop an approach to obtain the closed forms of the loops with specific properties, and try to generalize the conclusion to the general kinds of loops. The theoretical results are amazing. However, the examples in the paper are not enough, especially the applications of these theoretical results. In the section of related work, the authors list some possible applications including orbit problems and uniform terminations, but some applications should be implemented and discussed in details in this paper. This will make this work more convincing and meaningful in the view of computer science.

- Some theorems are not well-known or can not be proved straightforward, so the proof details should be displayed in a clear way. For example, Theorem 3.1 is a corollary of the eigenvalue theorem of linear algebra, but the part after "Moreover" shows some particular cases which need detailed proof. Maybe because of the limitation of paper pages, some proofs are omitted, but it would be better if they were included. 

- In the section 6.2, they discuss the recursive procedures, and regard the recursive procedures as loops. However, in the real world code, the recursive procedures might not be self-recursive, and mutual recursion is also a frequent-used pattern. Their modeling method can not be applied to mutual recursion, because the path of functions in the recursion is nondeterministic, which makes the outer function impossible to be modeled as a linear algebra system.