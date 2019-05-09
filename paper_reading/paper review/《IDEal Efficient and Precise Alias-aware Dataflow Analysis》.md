### IDEal: Efficient and Precise Alias-aware Dataflow Analysis
In this paper, authors presented IDEal, an extension to IDE framework to handle aliases in a precise and efficient manner. IDEal has the following features.
- Sound strong updates
- Individual propagation of pointers

IDEal can reuse fine-grained procedure summaries, which contributes to a considerable improvement in efficiency. It relieves the burden of alias information encoding in the dataflow domain, and provides an accessible approach to implement a wide range of dataflow analyses that track object flows.
#### Overview
The workflow of IDEal consists of two consecutive phases: the object-flow propagation(Phase OF) and the value-flow propagation(Phase VF). Meanwhile, IDEal takes the advantages of typestate analysis by defining a concrete lattice L and the respective environment transformers.
#### Design
The details of the main algorithm in IDEal include the standard flow functions definition in IDEal, how to handle points of aliasing, how to perform sound strong updates, and how to support context-sensitive alias queries. The following figure illustrates the definitions of the intraprocedural normal-flow functions of IDEal.
![1](D:\HKUST\论文笔记\Pic\3.JPG)
The fixed-point iteration of IDE is controlled by a function defined in the following figure. In the function PROPAGATE, two changes are introduced. A node of the OFG can be a point of aliasing, and the necessary aliases are computed by a pointer analysis. The call of COMPUTEALIASES abstracts the construction. The second change affects the propagation during Phase VF. Some of the points of aliasing introduce strong updates.
![2](D:\HKUST\论文笔记\Pic\4.JPG)
Strong updates can only be performed in Phase VF, once all necessary alias queries have already been performed in Phase OF and the results are known.