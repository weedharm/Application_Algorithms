# Applied Algorithms (C++)

My C++ solutions to the weekly training sets of the **Applied Algorithms** course (Thuật toán ứng dụng) at Hanoi University of Science and Technology (HUST), semester 20201. The problems were submitted on the course's private Codeforces group. They cover the core topics of the course: basic arithmetic and overflow, stacks and sweeps, exhaustive search with backtracking and branch-and-bound, binary search on the answer, dynamic programming, graph algorithms and greedy methods.

The problem statements (exported from the course's Codeforces group, mostly in English, some in Vietnamese) are in [`TTUD_Codeforces/problems/`](TTUD_Codeforces/problems).

## Repository structure

```
TTUD_Codeforces/
  01*.cpp ... 07*.cpp   solutions; the two-digit prefix is the training set, the rest is the problem name
  I-Tower.cpp, TOWER.cpp, K-MST.cpp, NETWORK.cpp
                        solutions without a set prefix (TOWER and NETWORKS are in set 05, K-MST in set 06)
  problems/
    01problems.pdf ... 07problems.pdf   problem statements of each training set
    cau_lieu.ipynb                      small Python scratch notebook (primality check)
```

## Getting started

Each file is a standalone program that reads from standard input and writes to standard output.

```bash
cd TTUD_Codeforces
g++ -std=c++17 -O2 -o hist 02HIST.cpp
./hist < input.txt
```

All 69 `.cpp` files compile with GCC 13 (`g++ -std=c++17`). No test data is included; the sample inputs are in the problem PDFs.

## Problem index

Status "unfinished" means the file is a stub or a partial attempt that does not solve the problem.

### Set 01: warm-up

| Problem | File | Description | Technique |
|---|---|---|---|
| ADD | [01ADD.cpp](TTUD_Codeforces/01ADD.cpp) | Sum of two integers close to the 64-bit limit | Splitting off the last digit to avoid overflow |
| ADDMOD | [01ADDMOD.cpp](TTUD_Codeforces/01ADDMOD.cpp) | (a + b) mod 10^9+7 | Modular arithmetic |
| EXPMOD | [01EXPMOD.cpp](TTUD_Codeforces/01EXPMOD.cpp) | a^b mod 10^9+7 with a, b up to 1.8 * 10^19 | Exponent reduction with Fermat's little theorem |
| SUBSEQMAX | [01SUBSEQMAX.cpp](TTUD_Codeforces/01SUBSEQMAX.cpp) | Maximum-sum contiguous subsequence | Kadane's algorithm |
| SUMSEQ | [01SUMSEQ.cpp](TTUD_Codeforces/01SUMSEQ.cpp) | Sum of a sequence mod 10^9+7 | Modular arithmetic |
| Way Too Long Words | [01WayTooLongWords.cpp](TTUD_Codeforces/01WayTooLongWords.cpp) | Abbreviate words longer than 10 characters | String handling |

### Set 02: data structures and sweeps

| Problem | File | Description | Technique |
|---|---|---|---|
| HIST | [02HIST.cpp](TTUD_Codeforces/02HIST.cpp) | Largest rectangle in a histogram | Monotonic stack (nearest smaller on each side) |
| POSTMAN | [02POSTMAN.cpp](TTUD_Codeforces/02POSTMAN.cpp) | Minimum travel distance to deliver packages on a line with a capacity-k vehicle | Greedy, farthest customers first |
| LOCATE | [02LOCATE.cpp](TTUD_Codeforces/02LOCATE.cpp) | Best translation matching two radar grids | Counting translation vectors with a map |
| WATERJUG BFS | [02WATERJUG_BFS.cpp](TTUD_Codeforces/02WATERJUG_BFS.cpp) | Minimum steps to measure c litres with two jugs | BFS over (jug A, jug B) states |
| REROAD | [02RELOAD.cpp](TTUD_Codeforces/02RELOAD.cpp) | Road "bumpiness" (number of segment runs) after each repair | O(1) incremental update per query |
| SIGNAL | [02SIGNAL.cpp](TTUD_Codeforces/02SIGNAL.cpp) | Best separation point between two peaks of a signal | Prefix and suffix maxima |
| SORT INT | [02SORTINT.cpp](TTUD_Codeforces/02SORTINT.cpp) | Sort a sequence of integers | `std::sort` |
| PARENTHESES | [02PARENTHESES.cpp](TTUD_Codeforces/02PARENTHESES.cpp) | Check whether a bracket string is balanced | Stack |
| Bracket Sequence | [02BracketSequense.cpp](TTUD_Codeforces/02BracketSequense.cpp) | Unfinished | Stack (helpers only) |

### Set 03: exhaustive search, backtracking, branch and bound

| Problem | File | Description | Technique |
|---|---|---|---|
| TSP | [03TSP.cpp](TTUD_Codeforces/03TSP.cpp) | Travelling salesman tour of minimum cost | Backtracking with branch and bound |
| KNAPSAC | [03KNAPSAC.cpp](TTUD_Codeforces/03KNAPSAC.cpp) | 0/1 knapsack | Backtracking |
| BCA | [03BCA.cpp](TTUD_Codeforces/03BCA.cpp) | Balanced course assignment to teachers with conflicts | Backtracking with branch and bound |
| CBUS | [03CBUS.cpp](TTUD_Codeforces/03CBUS.cpp) | Shortest bus route picking up and dropping off n passengers, capacity k | Backtracking with branch and bound |
| BACP | [03BACP.cpp](TTUD_Codeforces/03BACP.cpp) | Balanced academic curriculum with prerequisites | Backtracking with branch and bound |
| TAXI | [03TAXI.cpp](TTUD_Codeforces/03TAXI.cpp) | Shortest taxi route serving n passengers one at a time | Backtracking with branch and bound |
| CVRPCOUNT | [03CVRPCOUNT.cpp](TTUD_Codeforces/03CVRPCOUNT.cpp) | Count feasible capacitated vehicle routing solutions | Backtracking |
| CVRP OPT | [03CVRP_OPT.cpp](TTUD_Codeforces/03CVRP_OPT.cpp) | Minimum-cost capacitated vehicle routing | Backtracking |
| CNK | [03CNK.cpp](TTUD_Codeforces/03CNK.cpp) | C(n, k) mod m | Counting by enumerating combinations |
| CNK RM | [03CNKRM.cpp](TTUD_Codeforces/03CNKRM.cpp) | C(n, k) | Counting by enumerating combinations |
| DIGITS | [03DIGITS.cpp](TTUD_Codeforces/03DIGITS.cpp) | Count digit assignments with ICT - K62 + HUST = N | Backtracking over distinct digits |
| PERMUTATIONGEN | [03PERMUTATIONGEN.cpp](TTUD_Codeforces/03PERMUTATIONGEN.cpp) | Next permutation in lexicographic order | Next-permutation algorithm |
| PERMUTATIONLIST | [03PERMUTATIONLIST.cpp](TTUD_Codeforces/03PERMUTATIONLIST.cpp) | k-th permutation of 1..n | Backtracking |
| COMBINATIONGEN | [03COMBINATIONGEN.cpp](TTUD_Codeforces/03COMBINATIONGEN.cpp) | Next k-combination | Next-combination algorithm |
| COMBINATIONLIST | [03COMBINATIONLIST.cpp](TTUD_Codeforces/03COMBINATIONLIST.cpp) | k-th combination | Repeated next-combination |
| BINARYGEN | [03BINARYGEN.cpp](TTUD_Codeforces/03BINARYGEN.cpp) | Next binary string | Next-configuration generation |
| BINARYLIST | [03BINARYLIST.cpp](TTUD_Codeforces/03BINARYLIST.cpp) | k-th binary string of length n without i consecutive zeros | Backtracking |
| HOLEY N QUEENS | [03HOLEY_N_QUEENS.cpp](TTUD_Codeforces/03HOLEY_N_QUEENS.cpp) | Count N-queens placements on a board with holes | Backtracking with diagonal marks |
| NURSE | [03NURSE.cpp](TTUD_Codeforces/03NURSE.cpp) | Count nurse work plans with work periods of length k1..k2 | Backtracking |
| KPATH | [03K-PATH.cpp](TTUD_Codeforces/03K-PATH.cpp) | Count simple paths with exactly k edges | Backtracking |
| ROUTING | [03ROUTING.cpp](TTUD_Codeforces/03ROUTING.cpp) | Cheapest bicycle route through a given set of spots | Backtracking over the visiting order |
| CONTAINER | [03CONTAINER.cpp](TTUD_Codeforces/03CONTAINER.cpp) | Can N rectangles be packed into a container? | Total-area check only (not a full packing search) |

### Set 04: binary search and divide and conquer

| Problem | File | Description | Technique |
|---|---|---|---|
| PIE | [04PIE.cpp](TTUD_Codeforces/04PIE.cpp) | Largest equal pie piece for F + 1 people | Binary search on a real-valued answer |
| EKO | [04EKO.cpp](TTUD_Codeforces/04EKO.cpp) | Highest saw height that still yields M metres of wood | Binary search on the answer |
| AGGRCOW | [04AGGRCOW.cpp](TTUD_Codeforces/04AGGRCOW.cpp) | Maximise the minimum distance between C cows | Binary search on the answer |
| Lost Numbers | [04Lost_Numbers.cpp](TTUD_Codeforces/04Lost_Numbers.cpp) | Interactive: recover a permutation of 6 known numbers from 4 product queries | Lookup table of pairwise products |
| TRIPLE | [04TRIPLE.cpp](TTUD_Codeforces/04TRIPLE.cpp) | Count triples with a_i + a_j + a_k = K | Sorting and binary search |
| CLOPAIR | [04CLOPAIR.cpp](TTUD_Codeforces/04CLOPAIR.cpp) | Closest pair of points; unfinished (input only) | |
| FIBOWORDS | [04FIBOWORDS.cpp](TTUD_Codeforces/04FIBOWORDS.cpp) | Unfinished (empty `main`) | |

### Set 05: dynamic programming

| Problem | File | Description | Technique |
|---|---|---|---|
| GOLD MINING | [05GOLD_MINING.cpp](TTUD_Codeforces/05GOLD_MINING.cpp) | Maximum gold from warehouses picked at distances between L1 and L2 | DP over a sliding window |
| NETWORKS | [NETWORK.cpp](TTUD_Codeforces/NETWORK.cpp) | Minimum-cost k-route in a tree-shaped network | Tree DP |
| TOWER | [I-Tower.cpp](TTUD_Codeforces/I-Tower.cpp), [TOWER.cpp](TTUD_Codeforces/TOWER.cpp) | Tower of Babylon: tallest stack of blocks | DP over block rotations (LIS-style), two versions |
| INCREASE SUBSEQ | [05INCREASE_SUBSEQ.cpp](TTUD_Codeforces/05INCREASE_SUBSEQ.cpp) | Longest increasing subsequence | O(n^2) DP |
| MAX SUBSEQUENCE | [05MAX_SUBSEQUENCE.cpp](TTUD_Codeforces/05MAX_SUBSEQUENCE.cpp) | Maximum-sum contiguous subsequence | DP |
| RMQ | [05RMQ.cpp](TTUD_Codeforces/05RMQ.cpp) | Sum of range-minimum queries | Sparse table |
| NURSE | [05NURSE.cpp](TTUD_Codeforces/05NURSE.cpp) | Unfinished (input only); see 03NURSE for the backtracking version | |

### Set 06: graphs

| Problem | File | Description | Technique |
|---|---|---|---|
| CONNECTED COMPONENTS | [06CONNECTED_COMPONENTS.cpp](TTUD_Codeforces/06CONNECTED_COMPONENTS.cpp) | Number of connected components | DFS |
| BIPARTIE GRAPH | [06BIPARTIE_GRAPH.cpp](TTUD_Codeforces/06BIPARTIE_GRAPH.cpp) | Is the graph bipartite? | BFS 2-colouring |
| ARTICULATION POINTS N BRIDGES | [06ARTICULATION_POINTS_N_BRIDGES.cpp](TTUD_Codeforces/06ARTICULATION_POINTS_N_BRIDGES.cpp) | Unfinished (DFS skeleton, no output) | |
| STRONGLY CONNECTED COMPONENTS | [06STRONGLY_CONNECTED_COMPONENTS.cpp](TTUD_Codeforces/06STRONGLY_CONNECTED_COMPONENTS.cpp) | Number of strongly connected components | Counts DFS trees only; not a full Tarjan/Kosaraju |
| K-MST | [06K-MST.cpp](TTUD_Codeforces/06K-MST.cpp), [K-MST.cpp](TTUD_Codeforces/K-MST.cpp) | Minimum-weight tree with exactly k edges | Backtracking with union-find, two versions |
| COUNT SPANNING TREES | [06COUNT_SPANNING_TREES.cpp](TTUD_Codeforces/06COUNT_SPANNING_TREES.cpp) | Count spanning trees of a small graph | Backtracking over edge subsets with union-find |
| LONGEST PATH ON A TREE | [06LONGEST_PATH_ON_A_TREE.cpp](TTUD_Codeforces/06LONGEST_PATH_ON_A_TREE.cpp) | Weighted diameter of a tree | Two BFS passes |
| SHORTEST PATH PRIORITY QUEUE | [06SHORTEST_PATH_PRIORITY_QUEUE.cpp](TTUD_Codeforces/06SHORTEST_PATH_PRIORITY_QUEUE.cpp) | Shortest path from s to t in a weighted digraph | Dijkstra with a priority queue |
| MINIMUM SPANNING TREE | [06MINIMUM_SPANNING_TREE.cpp](TTUD_Codeforces/06MINIMUM_SPANNING_TREE.cpp) | Weight of a minimum spanning tree | Kruskal with union-find |
| FINDPARENT | [06FINDPARENT.cpp](TTUD_Codeforces/06FINDPARENT.cpp) | Parent of every node in a rooted tree | BFS |
| LCOUNT | [06LCOUNT.cpp](TTUD_Codeforces/06LCOUNT.cpp) | Number of leaves of a rooted tree | BFS and node degrees |
| ELEVTRBL | [06ELEVTRBL.cpp](TTUD_Codeforces/06ELEVTRBL.cpp) | Fewest elevator button presses from floor s to g | BFS |
| BUGLIFE | [06BUGLIFE.cpp](TTUD_Codeforces/06BUGLIFE.cpp) | Detect "suspicious" bug interactions | Bipartite check with BFS |

### Set 07: greedy

| Problem | File | Description | Technique |
|---|---|---|---|
| CHANGE | [07CHANGE.cpp](TTUD_Codeforces/07CHANGE.cpp) | Fewest notes to give change from 1000$ | Greedy on denominations |
| Planting Trees | [07Planting_Trees.cpp](TTUD_Codeforces/07Planting_Trees.cpp) | Earliest party day after planting all trees | Greedy, slowest-growing first |
| ATM | [07ATM.cpp](TTUD_Codeforces/07ATM.cpp) | Fewest notes for an ATM withdrawal | Greedy on denominations |

## Tech stack

C++ (C++11/14 features such as range-based `for` and lambdas; built with `g++ -std=c++17`), standard library only.

## Context

University course work, HUST, semester 20201 (2020). Code comments are partly in Vietnamese.

## License

[MIT](LICENSE)
