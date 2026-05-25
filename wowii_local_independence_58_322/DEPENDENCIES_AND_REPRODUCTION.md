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
