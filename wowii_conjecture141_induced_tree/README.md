# Formal Proof Artifact for WOWII Conjecture 141

This directory contains the Lean formal proof artifact supporting the manuscript
`A Verified Proof of Written on the Wall II Conjecture 141`.

## Target

- Paper theorem: Written on the Wall II Conjecture 141, ceil version.
- Public repository:
  `https://github.com/chainstart/wowii-conjecture141-formal-proof`
- Lean theorem:
  `WrittenOnTheWallII.GraphConjecture141.conjecture141_strong`
- Main source file:
  `FormalConjectures/WrittenOnTheWallII/GraphConjecture141.lean`

The formal statement is:

```lean
theorem conjecture141_strong (G : SimpleGraph α) (h : G.Connected) :
    (G.girth + 1) / 2 - 1 + (Finset.univ.sup (indepNeighborsCard G)) ≤
    largestInducedTreeSize G := by
```

Here `(G.girth + 1) / 2` is the natural-number encoding of
`ceil(girth(G) / 2)`.

## Contents

- `FormalConjectures/`: Lean source tree containing the theorem file.
- `FormalConjecturesForMathlib/`: companion source tree required by the project.
- `FormalConjecturesForMathlib.lean`: root module for the companion source tree.
- `FormalConjecturesTest/`: test/source support from the upstream project.
- `scripts/`: Lean helper script directory referenced by `lakefile.toml`.
- `lakefile.toml`: Lake project configuration.
- `lake-manifest.json`: pinned dependency manifest.
- `lean-toolchain`: Lean toolchain pin.
- `natural_language_proof.md`: informal proof exposition.
- `verification_report.json`: local verification report.
- `DEPENDENCIES_AND_REPRODUCTION.md`: dependency and reproduction instructions.

Build caches such as `.lake/` are intentionally not included.
