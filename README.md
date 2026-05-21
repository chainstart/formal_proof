# Formal Proof Support Materials

This repository contains Lean formal proof support materials for the manuscript

**A Verified Proof of Written on the Wall II Conjecture 141**.

The paper-specific artifact is in:

```text
wowii_conjecture141_induced_tree/
```

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
