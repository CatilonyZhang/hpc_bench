
# Optimization Loop Continuation

You encounter this prompt because you have finish one round of iteration of optimzation, and for some reason you have stop your session.

You should now keep working on this project.


First, it is best to review the following files.

- `task.md`
- `submission_example.md`
- `report_guidance.md`
- `cluster.md`
- `./resources/` if available

Then continue the optimization work.

## Checklist

Before starting a new round, consider the following questions.

- Have you make use of domain knowledge in `./resource` ?

- Have you propose some stosicate paramter instead of grid-scanning them ? Can you explain how you do this?

- Have you write down your optimization steps?

Have you try or think about :

- Compiler optimizations: Use of different compilers (Intel, GCC, AOCC and any other avaible) and optimization flags? exploare as much as you can

- Mathematical libraries: Integration of optimized BLAS/LAPACK libraries (Intel MKL, OpenBLAS, AOCL and any other available?)

- Parallel strategies: MPI configuration, hybrid parallelization, process placement and affinity, and thread management and so on

- Software tuning like HDF5 OR MPI?(if appiable)

- Communication optimization: Reducing communication overhead and latency

- System-level tuning: CPU frequency scaling, NUMA topology optimization, file system and storage access ? 

- Have you use or install any profiler to analysis IO or memory , communcation usage? Have you try different or new profilers?

- Have you try all those methods ? you can use online search , or any other way to try to optimize the performance,  you should do this as much as possible 

- Have you try to compile or build some of the dependency? This might change performance.

You should updated your submission in time or everytime you make a new progress.

please refer to `task.md` `submission_example.md` `./report_guidance.md` `./submission_example` `./cluster.md` for more detail

Your optimization is highly valued.

The following sessions are for you to take notes, make todos or take down some milestore for yourself to refer to.

This file is `loop.md`,feel free to edit section below

## TODOS:

