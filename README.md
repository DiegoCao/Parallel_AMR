Group Members:

Xingyuan Wang (xingyuaw@andrew.cmu.edu)
Hangrui Cao (hangruic@andrew.cmu.edu)

# Project Proposal


## SUMMARY

We plan to implement and optimize an Adaptive Mesh Refinement (AMR) framework specifically designed for stencil computations on parallel computing systems, including both multi-core CPUs and NVIDIA GPUs available in our lab. Our focus will be on creating a scalable and efficient solution that dynamically adjusts the computational grid for high-resolution simulations in regions of interest, significantly improving computation time and resource utilization.

## BACKGROUND
The core application of our project involves solving partial differential equations (PDEs) that are common in various scientific and engineering fields, such as fluid dynamics, electromagnetics, and material science. Stencil computations, which update each grid point's value based on its neighbors, are a critical component of these simulations. Adaptive Mesh Refinement (AMR) optimizes these computations by increasing the grid resolution only where needed, based on error estimates or feature detection. This approach can significantly reduce the number of computations and memory usage while maintaining or even improving the accuracy of the simulation.

## THE CHALLENGE
Workload Characteristics: Stencil computations have a high degree of spatial locality but may face challenges in terms of load imbalance due to the adaptive nature of AMR. Dependencies between grid points also introduce synchronization overhead in parallel environments.
System Constraints: Mapping the AMR-enabled stencil computations to parallel architectures poses challenges, including efficiently distributing the dynamically changing workload across processors and minimizing communication overhead between them.
What We Hope to Learn: We aim to explore strategies for dynamic load balancing, effective parallelization of AMR processes, and optimization of memory access patterns in stencil computations to achieve high performance on parallel systems.

## RESOURCES
Computing Resources: Access to the university's HPC cluster with multi-core CPUs.
Starter Code: We will start from an existing open-source AMR implementations (which include the serial implementation version), extending and optimizing it for our needs.
Reference Material: We will base our AMR strategy on the principles outlined in "Berger, M. J., and Oliger, J. Adaptive Mesh Refinement for Hyperbolic Partial Differential Equations." Journal of Computational Physics, 1984.

## GOALS AND DELIVERABLES:

Plan to Achieve:
Implement a basic AMR framework capable of dynamic mesh refinement and coarsening for stencil computations.
Achieve at least a 5x speed-up on AMR-enabled stencil computations compared to uniform grid computations for selected PDEs.
Hope to Achieve:
Extend the optimization to achieve a 10x speed-up and explore the use of machine learning techniques for predicting regions requiring refinement.
Demo: We plan to show a live simulation of fluid flow around an obstacle, comparing the performance and accuracy with and without AMR. Speedup graphs and resource utilization metrics will also be presented.

## PLATFORM CHOICE
We have chosen to work with Pittsburgh PSC Machines, which include 128 cores to run parallel MPI program. 

## SCHEDULE
Week 1-2: Literature review and finalization of the project design.
Week 3-4: Basic implementation of the AMR framework.
Week 5-6: Integration of the AMR framework with MPI.
Week 7-10: Testing, validation, and benchmarking against uniform grid solutions.
Week 11: Preparation of the final report and development of the demo.
Intermediate Milestone (April 16th): Completed basic AMR framework with integrated stencil computations.
This schedule allows us to allocate time efficiently, considering the project's complexity and our academic workload. We plan to reassess our progress weekly to ensure we stay on track to meet our goals.

