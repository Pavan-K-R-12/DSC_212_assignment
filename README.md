# DSC212 – Modularity on the Karate Club Graph

Recursive spectral modularity bisection (Newman 2006) implemented from scratch with NumPy + NetworkX.

- `karate_modularity.ipynb` – full notebook (runs top-to-bottom, no manual edits; outputs included)
- `assets/` – figures written by the notebook (partition after each split, metric evolution, variant comparison)

## Run
```bash
pip install numpy pandas networkx matplotlib jupyter
jupyter nbconvert --to notebook --execute --inplace karate_modularity.ipynb
```

## Headline result
5 communities, Q = 0.409; first split recovers the real club fission with 1/34 node misclassified (node 8).
