# Dependencies And Reproduction

This package is intended to be checked with Lean 4 and Lake.

## Versions

- Lean toolchain: `leanprover/lean4:v4.27.0`
- Mathlib revision: `a3a10db0e9d66acbebf76c5e6a135066525ac900`

## Fresh Reproduction

From a fresh clone of the public repository:

```bash
cd formal_proof/wowii_local_girth_induced_tree
lake exe cache get
lake build FormalConjectures.WrittenOnTheWallII.GraphConjecture141
rg -n "\bsorry\b|\badmit\b|axiom|constant|opaque" FormalConjectures/WrittenOnTheWallII/GraphConjecture141.lean
```

The final `rg` command should print no lines for the target file.

## Verified Declarations

- `WrittenOnTheWallII.GraphConjecture141.local_girth_induced_tree_bound`
- `WrittenOnTheWallII.GraphConjecture141.conjecture140_from_local_girth_strong`
- `WrittenOnTheWallII.GraphConjecture141.conjecture141_from_local_girth_strong`
