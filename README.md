Group Members:

Xingyuan Wang (xingyuaw@andrew.cmu.edu)
Hangrui Cao (hangruic@andrew.cmu.edu)

# Project Proposal


## Summary

We aim to parallelize and optimize an Adaptive Mesh Refinement (AMR) code using OpenMP. The project involves parallelizing an existing serial base code to leverage parallel processing, potentially exploring techniques to reduce lock contention, thus enhancing its performance and scalability.

## BACKGROUND
The core application of our project involves solving partial differential equations (PDEs) that are common in various scientific and engineering fields, such as fluid dynamics, electromagnetics, and material science. Stencil computations, which update each grid point's value based on its neighbors, are a critical component of these simulations. Adaptive Mesh Refinement (AMR) optimizes these computations by increasing the grid resolution only where needed, based on error estimates or feature detection. This approach can significantly reduce the number of computations and memory usage while maintaining or even improving the accuracy of the simulation.

## THE CHALLENGE
Workload Characteristics: Stencil computations have a high degree of spatial locality but may face challenges in terms of load imbalance due to the adaptive nature of AMR. Dependencies between grid points also introduce synchronization overhead in parallel environments.

**System Constraints**: Mapping the AMR-enabled stencil computations to parallel architectures poses challenges, including efficiently distributing the dynamically changing workload across processors and minimizing communication overhead between them.


**What We Hope to Learn**: We aim to explore strategies for dynamic load balancing, effective parallelization of AMR processes, and optimization of memory access patterns in stencil computations to achieve high performance on parallel systems.

## RESOURCES
**Computing Resources**: Access to the university's HPC cluster with multi-core CPUs.
Starter Code: We will start from an existing open-source AMR implementations (which include the serial implementation version), extending and optimizing it for our needs.

**Reference Material**: We will base our AMR strategy on the principles outlined in "Berger, M. J., and Oliger, J. Adaptive Mesh Refinement for Hyperbolic Partial Differential Equations." Journal of Computational Physics, 1984.

## GOALS AND DELIVERABLES:

**Plan to Achieve**:
Implement a basic AMR framework capable of dynamic mesh refinement and coarsening for stencil computations.
Achieve at least a 5x speed-up on AMR-enabled stencil computations compared to uniform grid computations for selected PDEs.

**Hope to Achieve**:
Extend the optimization to achieve a 10x speed-up and explore the use of machine learning techniques for predicting regions requiring refinement.

**Demo**: We plan to show a live simulation of fluid flow around an obstacle, comparing the performance and accuracy with and without AMR. Speedup graphs and resource utilization metrics will also be presented.

## PLATFORM CHOICE
We have chosen to work with Pittsburgh PSC Machines, which include 128 cores to run parallel MPI program. 

## SCHEDULE

| Week | Dates               | Tasks                                                                                     |
|------|---------------------|-------------------------------------------------------------------------------------------|
| 0    | March 25 – March 31 | Literature review and finalization of the high-level project design.                      |
| 1    | April 1 – April 7   | Basic implementation of the AMR framework. Understand the baseline code.                  |
| 2    | April 8 – April 14  | Integration of the AMR framework with MPI. Basic parallelism finished with test results on GHC machines. |
| 3    | April 15 – April 21 | Testing, validation, and benchmarking against uniform grid solutions. Optimize work balance and reduce communication overhead. |
| 4    | April 22 – April 28 | Keep optimizing the solution, but with a focus on reducing lock and contention. Obtain experimental results from PSC machines. |
| 5    | April 29 – May 5    | Finish up comparison analysis, final report, and poster preparation.                        |

This schedule allows us to allocate time efficiently, considering the project's complexity and our academic workload. We plan to reassess our progress weekly to ensure we stay on track to meet our goals.

