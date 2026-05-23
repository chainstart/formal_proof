# Dependencies And Reproduction

This package is intended to be checked with Lean 4 and Lake.

## Versions

- Lean toolchain: `leanprover/lean4:v4.26.0`
- Mathlib revision: `2df2f0150c275ad53cb3c90f7c98ec15a56a1a67`

## Fresh Reproduction

From a fresh clone of the public repository:

```bash
cd formal_proof/wowii_conjecture13_induced_bipartite
lake exe cache get
lake build AmraLibrary.Combinatorics.SimpleGraph.GraphConjectures.WowiiConjecture13
rg -n "\bsorry\b|\badmit\b|axiom|constant|opaque" AmraLibrary/Combinatorics/SimpleGraph/GraphConjectures/WowiiConjecture13.lean
```

The final `rg` command should print no lines for the target file.

## Verified Declarations

- `SimpleGraph.conjecture13`
- `SimpleGraph.diam_add_indepNeighborsCard_sub_one_le_largestInducedBipartiteSubgraphSize`
