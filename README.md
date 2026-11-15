# Modularity on the Karate Club Graph (DSC212)

Recursive spectral modularity partitioning (Newman, 2006) on Zachary's Karate Club network, using only NumPy and NetworkX.

**Files**
- `karate_modularity.ipynb`: the notebook (runs top to bottom, outputs included)
- `assets/`: the figures produced by the notebook

## Process

1. **Build the modularity matrix.** From the adjacency matrix `A` and degrees `k`, compute `B = A - k kᵀ / 2m`. `B[i][j]` is how much more connected `i` and `j` are than expected by chance.
2. **Split one community.** Take the block of `B` for the community, find its leading eigenvector, and put nodes with a positive entry in one group and the rest in the other. If the leading eigenvalue is ≤ 0, the community is not split.
3. **Repeat.** Start with all nodes in one community and apply step 2 to every new community until none can be split. Each split is one iteration and the partition is saved after each one.
4. **Visualise.** Draw the graph after each iteration with a fixed layout, one colour per community.
5. **Compute metrics.** After each iteration, compute degree, betweenness and closeness centrality and the clustering coefficient for every node, inside its own community.
6. **Plot.** Plot each metric against the iteration number, one line per node.

## Reference
M. E. J. Newman (2006). Modularity and community structure in networks. *PNAS* 103(23):8577–8582.
