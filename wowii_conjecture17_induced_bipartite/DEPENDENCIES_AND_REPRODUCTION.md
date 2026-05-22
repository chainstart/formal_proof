# Dependencies And Reproduction

This package is intended to be checked with Lean 4 and Lake.

## Versions

- Lean toolchain: `leanprover/lean4:v4.27.0`
- Mathlib revision: `v4.27.0`

## Fresh Reproduction

From a fresh clone of the public repository:

```bash
cd formal_proof/wowii_conjecture17_induced_bipartite
lake exe cache get
lake build FormalConjectures.WrittenOnTheWallII.GraphConjecture17
rg -n "\bsorry\b|\badmit\b|axiom|constant|opaque" FormalConjectures/WrittenOnTheWallII/GraphConjecture17.lean
```

The final `rg` command should print no lines for the target file.

## Verified Declarations

- `WrittenOnTheWallII.GraphConjecture17.conjecture17_nat_bound`
- `WrittenOnTheWallII.GraphConjecture17.conjecture17_real_bound`
- `WrittenOnTheWallII.GraphConjecture17.conjecture17`
