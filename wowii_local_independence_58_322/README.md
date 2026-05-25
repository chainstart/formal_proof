# WOWII local-neighborhood independence support package

This Lean package supports the manuscript on two Written on the Wall II
statements governed by local-neighborhood independence.

It contains:

- `WowiiConjecture58`: a certified 61-vertex counterexample to the proposed
  local-average induced-forest inequality.
- `WowiiConjecture322`: a certified local-clique rigidity theorem implying
  well total domination under the WOWII 322 hypotheses.

Build the package with:

```bash
lake build
```

The root import is `AmraLibrary`.
