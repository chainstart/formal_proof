# Dependencies And Reproduction

This package is intended to be checked with Lean 4 and Lake.

## Versions

- Lean toolchain: `leanprover/lean4:v4.26.0`
- Mathlib revision: `2df2f0150c275ad53cb3c90f7c98ec15a56a1a67`

## Fresh Reproduction

From a fresh clone of the public repository:

```bash
cd formal_proof/wowii_conjecture58_counterexample
lake exe cache get
lake build AmraLibrary.Combinatorics.SimpleGraph.GraphConjectures.WowiiConjecture58
rg -n "\bsorry\b|\badmit\b|axiom|constant|opaque" AmraLibrary/Combinatorics/SimpleGraph/GraphConjectures/WowiiConjecture58.lean
```

The final `rg` command should print no lines for the target file.

## Verified Declarations

- `SimpleGraph.wowii_conjecture58_counterexample_certified`
- `SimpleGraph.Wowii58Vertex.l_avg_eq`
