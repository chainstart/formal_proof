# Local Verification

This directory contains a Lean 4 / Lake copy of the local Formal Conjectures
workspace in which WOWII GraphConjecture17 was proved.

## Target

File:

`FormalConjectures/WrittenOnTheWallII/GraphConjecture17.lean`

The main declaration is:

```lean
theorem conjecture17 (G : SimpleGraph α) (h : G.Connected) :
    (G.indepNum : ℝ) + ⌈(G.diam : ℝ) / 3⌉ ≤ b G := by
  exact conjecture17_real_bound G h
```

The surrounding FormalConjectures file has:

```lean
variable {α : Type*} [Fintype α] [DecidableEq α] [Nontrivial α]
```

so the certified formal target is the finite nontrivial connected simple-graph
case. If one allows the one-vertex connected graph in the informal source
wording, the missing case is immediate: `diam(G)=0`, `alpha(G)=1`, and the
whole one-vertex graph is an induced bipartite subgraph, so `b(G)=1`.

## Verification command

From this directory, run:

```bash
lake build FormalConjectures.WrittenOnTheWallII.GraphConjecture17
```

Verified locally on 2026-05-22 with:

```bash
lake exe cache get
lake build FormalConjectures.WrittenOnTheWallII.GraphConjecture17
```

The build completed successfully with `8002 jobs`.

The source file itself has no `sorry`, `admit`, `axiom`, or `opaque`
occurrences.

## Source alignment

The original WOWII resolved table states Conjecture 17 as:

```text
If G is a simple connected graph, then b(G) >= a(G) + CEIL(diam(G)/3).
```

The FormalConjectures statement uses `G.indepNum` for `a(G)=alpha(G)` and
`b G` for the number of vertices in a largest induced bipartite subgraph. This
matches the standard notation recorded in Douglas West's REGS notes, where
`alpha(G)` denotes maximum independent-set size and `b(G)` denotes the maximum
number of vertices in an induced bipartite subgraph.
