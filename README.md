# HIP-Ray-BVH-Traversal

This repo has different implementations of research papers for ray traversals.

1. Implemeted stackless restart trail traversal method : Based on the research paper [Restart Trail for Stackless BVH Traversal](https://research.nvidia.com/sites/default/files/pubs/2010-06_Restart-Trail-for/laine2010hpg_paper.pdf)

   This method maintains a trail which points to the node for which we have already tested the intersection. If we follow the trail we will reach the far node which is not yet tested for intersection. Every pop operation we restart the traversal from root node and follow the trail. Every pop we will update the trail so it points to right next node.
   This method is slow as we restart everytime from root node. Though I like this method for its simplicity. We just have one u64 trail thats it!
   For bunny the stack based method traversal time was 0.27 ms vs the restart trail takes 1.24 ms.
