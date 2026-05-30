# WOWII local-neighborhood independence support package

This Lean package supports the manuscript on two Written on the Wall II
statements governed by local-neighborhood independence.

It contains:

- `WowiiConjecture58`: a certified 61-vertex counterexample to the proposed
  local-average induced-forest inequality.
- `WowiiConjecture322`: a certified proof of the original WOWII 322
  complement-local-independence formulation.  The formal theorem shows that
  under the complement hypothesis every edge of `G` is a two-vertex total
  dominating set, so all minimal total dominating sets have cardinality two.

Build the package with:

```bash
lake build
```

The root import is `AmraLibrary`.
