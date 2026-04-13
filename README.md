# Project I — Undirected Graph in C

## Overview
This project implements an **undirected graph** data structure G = (V, E) using the C programming language.

The input graph is loaded from a text file sourced from the SNAP dataset (Stanford Network Analysis Project), specifically from the Road Networks collection:  
http://snap.stanford.edu/data/index.html

---

## Features
The program supports the following core graph operations:

- Breadth-First Search (BFS)
- Depth-First Search (DFS)
- Vertex Cover Verification

---

## Vertex Cover Verification

A **vertex cover** is a set of vertices such that every edge in the graph is incident to at least one vertex in the set.

This project verifies whether a given set of vertices forms a valid vertex cover using the following approach:

### Algorithm

1. Read vertices from the input file sequentially.

2. For each vertex A in the set:

   - Traverse the adjacency list of A.

   - For each adjacent vertex `a`:
     - Traverse the adjacency list of `a`.
     - Find and remove vertex A from `a`'s adjacency list.
     - Once removed, proceed to the next adjacent vertex of A.

3. Repeat this process until the adjacency list of A becomes empty.

4. After processing all adjacent vertices:
   - Set the adjacency list of A to empty (effectively removing vertex A and all its incident edges from the graph).

5. Continue this process for all vertices in the given set.

---

## Final Check

- After all specified vertices are removed:
  - If the graph becomes **empty** (i.e., all adjacency lists are empty),  
    → the given set **is a valid vertex cover**.
  - Otherwise,  
    → the set **is NOT a vertex cover**.

---

## Notes
- The graph is represented using an adjacency list.
- Since the graph is undirected, every edge must be removed from both endpoints.
- Be careful with memory management when removing nodes in C to avoid memory leaks.
