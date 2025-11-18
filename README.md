# Dsc_assignment-212
Author: Thaya Lakshminarayanan G, Roll No: IMS24252

Modularity Analysis on the Karate Club Graph
DSC212 — Graph Theory · Assignment

This repository contains a complete implementation of recursive spectral modularity partitioning on Zachary’s Karate Club Graph, done as part of the DSC212 Research Assignment.
The goal of this project is to explore how community structures emerge from modularity optimization and how node-level metrics evolve across iterative spectral splits.

Project Overview

Community detection plays a central role in understanding real-world networks — from social graphs to biological systems.
In this project, I implement:

The modularity matrix

Leading eigenvector-based community splitting

Recursive bisection until eigenvalues ≤ 0

Visualizations after each split (consistent layout)

Evolution of:

Degree centrality

Betweenness centrality

Closeness centrality

Clustering coefficient

All results are produced using a single Jupyter notebook that runs top-to-bottom without manual edits.
Key Concepts Implemented
✔ 1. Modularity Matrix (B)
𝐵
=
𝐴
−
𝑘
𝑘
𝑇
2
𝑚
B=A−
2m
kk
T
	​


Where:

A = adjacency matrix

k = degree vector

m = number of edges

✔ 2. Spectral Bisection

Compute the leading eigenvalue λ₁ and eigenvector u₁ of B(C)

If λ₁ > 0 → split the community by sign(u₁)

If λ₁ ≤ 0 → stop splitting

✔ 3. Recursive Community Detection

The algorithm repeatedly splits communities until no subset can produce a positive eigenvalue.

✔ 4. Centrality Metric Evolution

After each iteration, for every node:

Degree centrality

Betweenness centrality

Closeness centrality

Clustering coefficient

are recorded and plotted to study how each metric responds to the changing community structure.
isual Outputs

The notebook automatically generates:

Graph visualizations after each recursive split
(with stable spring layout for fair comparison)

Metric evolution plots showing how each node's centrality changes

Iteration state logs stored in assets/iteration_state.json

karate-modularity/
├── DSC212_Karate_Modularity.ipynb     # Main notebook
├── README.md                          # This file
├── assets/
│   ├── layout_positions.npy           # Fixed node layout
│   ├── iteration_state.json           # Stored results per iteration
│   └── plots/                         # Auto-generated figures
└── LICENSE


