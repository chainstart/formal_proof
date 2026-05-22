# Dependencies and Reproduction Instructions

Public repository:

```text
https://github.com/chainstart/formal_proof
```

## Prerequisites

Install Lean through `elan`:

```bash
curl https://raw.githubusercontent.com/leanprover/elan/master/elan-init.sh -sSf | sh
```

Then open a new shell or source the `elan` environment file as instructed by the
installer.

## Pinned Versions

This artifact is a Lake project with:

- Lean toolchain: `leanprover/lean4:v4.27.0`
- Mathlib dependency: `leanprover-community/mathlib`, revision `v4.27.0`

The exact project pins are stored in:

```text
lean-toolchain
lakefile.toml
lake-manifest.json
```

## Reproduce the Formal Check

From the paper artifact directory:

```bash
git clone https://github.com/chainstart/formal_proof.git
cd formal_proof/wowii_conjecture141_induced_tree
lake exe cache get
lake build FormalConjectures.WrittenOnTheWallII.GraphConjecture141
```

The first command downloads precompiled Mathlib cache files when available. The
second command checks the Lean module containing the theorem.

Expected result:

```text
Build completed successfully
```

## Placeholder Scan

After a successful build, scan the theorem file for common proof placeholders:

```bash
rg -n "\\bsorry\\b|\\badmit\\b|axiom|constant|opaque" \
  FormalConjectures/WrittenOnTheWallII/GraphConjecture141.lean
```

Expected result: no matches.

## Target File

The theorem is located at:

```text
FormalConjectures/WrittenOnTheWallII/GraphConjecture141.lean
```

The theorem name is:

```text
WrittenOnTheWallII.GraphConjecture141.conjecture141_strong
```

## Notes

The upstream FormalConjectures repository may still contain the original
open/sorry version of `GraphConjecture141.lean`; this support package contains
the verified ceil-version proof used by the manuscript.
