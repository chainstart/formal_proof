# Dependencies and Reproduction

Toolchain: `leanprover/lean4:v4.26.0`

The Lake manifest pins mathlib and its transitive dependencies. To reproduce:

```bash
lake build
```

For focused checks:

```bash
lake build AmraLibrary.Combinatorics.SimpleGraph.GraphConjectures.WowiiConjecture58
lake build AmraLibrary.Combinatorics.SimpleGraph.GraphConjectures.WowiiConjecture322
```

The Conjecture 322 module exports `SimpleGraph.conjecture322`, whose
hypothesis is the original complement-local condition
`∀ v, indepNeighborsCard (Gᶜ) v ≤ 1`.
