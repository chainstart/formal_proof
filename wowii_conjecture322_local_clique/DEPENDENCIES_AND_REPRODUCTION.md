# Dependencies And Reproduction

This package is intended to be checked with Lean 4 and Lake.

## Versions

- Lean toolchain: `leanprover/lean4:v4.26.0`
- Mathlib revision: `2df2f0150c275ad53cb3c90f7c98ec15a56a1a67`

## Fresh Reproduction

From a fresh clone of the public repository:

```bash
cd formal_proof/wowii_conjecture322_local_clique
lake exe cache get
lake build AmraLibrary.Combinatorics.SimpleGraph.GraphConjectures.WowiiConjecture322
rg -n "\bsorry\b|\badmit\b|axiom|constant|opaque" AmraLibrary/Combinatorics/SimpleGraph/GraphConjectures/WowiiConjecture322.lean
```

The final `rg` command should print no lines for the target file.

## Verified Declarations

- `SimpleGraph.conjecture322`
- `SimpleGraph.connected_eq_top_of_indepNeighborsCard_le_one`
- `SimpleGraph.isWellTotallyDominated_top_of_two_le_card`
