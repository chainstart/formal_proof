# Formal Proof Support Materials

This repository is the shared public archive for Lean formal proof support
materials. The repository name is `formal_proof`; each concrete theorem or paper
proof package lives in its own top-level subdirectory.

Currently included proof packages:

```text
wowii_conjecture141_induced_tree/
```

That package supports the manuscript:

**A Verified Proof of Written on the Wall II Conjecture 141**.

The main verified Lean theorem is:

```text
WrittenOnTheWallII.GraphConjecture141.conjecture141_strong
```

The main source file is:

```text
wowii_conjecture141_induced_tree/FormalConjectures/WrittenOnTheWallII/GraphConjecture141.lean
```

For dependency versions and reproduction commands, see:

```text
wowii_conjecture141_induced_tree/DEPENDENCIES_AND_REPRODUCTION.md
```

The `.lake/` build cache is intentionally not tracked. Recreate it with:

```bash
cd wowii_conjecture141_induced_tree
lake exe cache get
lake build FormalConjectures.WrittenOnTheWallII.GraphConjecture141
```
