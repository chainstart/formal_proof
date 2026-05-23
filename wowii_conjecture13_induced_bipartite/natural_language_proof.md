# Proof Package: WOWII GraphConjecture13

Status: proved_candidate.

## Statement

For every connected finite simple graph `G`,

```text
b(G) >= diam(G) + max_v l(v) - 1,
```

where `b(G)` is the maximum order of an induced bipartite subgraph and
`l(v) = alpha(G[N(v)])`.

We prove the stronger per-vertex statement:

```text
for every vertex v, b(G) >= diam(G) + l(v) - 1.
```

Then choose a vertex maximizing `l(v)`.

## Proof

Fix a vertex `v`.  Let `A` be a maximum independent subset of `N(v)`, so
`|A| = l(v)`.

Let

```text
P = p_0, p_1, ..., p_D
```

be a diameter geodesic, so `D = diam(G)`.  Because `P` is geodesic, it is an
induced path: if `p_i` were adjacent to `p_j` with `i+1 < j`, then replacing
the subpath `p_i,...,p_j` by that single edge would shorten the path.

Define the short window

```text
Q = {p_i : dist(v,p_i) <= 2}.
```

This window has at most five vertices.  Indeed, if `p_i,p_j ∈ Q` and `i < j`,
then the geodesic property gives

```text
j - i = dist(p_i,p_j) <= dist(p_i,v) + dist(v,p_j) <= 4.
```

Thus all indices occurring in `Q` lie in an interval of length at most `4`.
Since the path has no repeated vertices, `|Q| <= 5`.

Every path-neighbor of a vertex in `A` lies in `Q`: if `a ∈ A` and
`a` is adjacent to `p_i`, then `v-a-p_i` is a walk of length `2`, so
`dist(v,p_i) <= 2`.  Also, `v` has no neighbor in `P \ Q`, since any path
vertex adjacent to `v` has distance `1` from `v`.

We now define a small set `T ⊆ Q` to add back after deleting `Q` from the path:

- If `|Q| <= 3`, let `T = ∅`.
- If `|Q| = 4`, choose one vertex of `Q` at distance exactly `2` from `v`.
  Such a vertex exists: otherwise all four vertices of `Q` would have distance
  at most `1` from `v`; the first and last of their path indices differ by at
  least `3`, contradicting
  `dist(p_i,p_j) <= dist(p_i,v)+dist(v,p_j) <= 2`.
- If `|Q| = 5`, let `T` be the two vertices of `Q` with minimum and maximum
  path index.  Their indices differ by `4`, and both are within distance `2`
  of `v`; hence both have distance exactly `2` from `v`, otherwise the
  triangle inequality through `v` would give a path shorter than four between
  them.

Now set

```text
S = (V(P) \ Q) ∪ A ∪ {v} ∪ T.
```

The pieces in this union are disjoint except for harmless set notation:

- `A` is disjoint from `V(P)\Q`, because every `a ∈ A` has distance `1` from
  `v`, while every vertex of `V(P)\Q` has distance at least `3`;
- `T` is disjoint from `A` and from `{v}`, since every vertex of `T` has
  distance exactly `2` from `v`;
- if `v` lies on `P`, then `v ∈ Q`, so it is not in `V(P)\Q`.

Let `q = |Q|` and `t = |T|`.  Then

```text
|S| = (D+1-q) + |A| + 1 + t.
```

By construction, `t = 0` for `q <= 3`, `t = 1` for `q = 4`, and `t = 2` for
`q = 5`.  Therefore in all cases

```text
|S| >= D + |A| - 1.
```

It remains to prove `G[S]` is bipartite.

Color `v` and all vertices of `T` with color `0`, and color every vertex of
`A` with color `1`.

The selected path vertices are `(V(P)\Q) ∪ T`.  Their induced subgraph is a
subgraph of the path `P`, because `P` is induced.  Each connected component of
this selected path subgraph contains at most one vertex of `T`:

- if `|Q| <= 3`, then `T` is empty;
- if `|Q| = 4`, then `T` has one vertex;
- if `|Q| = 5`, then `T` consists of the two extreme vertices of the five
  consecutive-index window `Q`, and the three middle vertices of `Q` are
  deleted, so the two vertices of `T` lie in different path components.

Thus each selected path component can be colored alternately along the path,
with its unique `T` vertex colored `0` if it has one.  Components without a
vertex of `T` are colored arbitrarily by path alternation.

Now check all possible induced edges in `S`.

- Edges among selected path vertices cross colors by the alternating path
  coloring.
- There are no edges inside `A`, since `A` is independent.
- Edges between `v` and `A` cross colors, by definition of `A ⊆ N(v)`.
- There is no edge from `v` to a selected path vertex: vertices of `V(P)\Q`
  have distance at least `3` from `v`, and vertices of `T` have distance
  exactly `2`.
- There is no edge from `A` to `V(P)\Q`, since such an edge would put the path
  vertex at distance at most `2` from `v`, hence in `Q`.
- Any edge from `A` to `T` crosses colors, because `A` has color `1` and
  `T` has color `0`.

So every edge of `G[S]` crosses the coloring, and `G[S]` is bipartite.

Since `S` is an induced bipartite subgraph of size at least
`D + |A| - 1 = diam(G) + l(v) - 1`, we have

```text
b(G) >= diam(G) + l(v) - 1.
```

This holds for every `v`.  Taking `v` with maximum `l(v)` proves
Conjecture 13.

## Sanity Checks Performed

The construction was tested computationally on:

- all connected unlabeled graphs on at most 7 vertices;
- every vertex `v`, every independent `A ⊆ N(v)`, and every diameter path in
  those graphs;
- the explicit 8-vertex counterexample to the old path-only conflict-cover
  lemma;
- random connected graphs on 8, 9, and 10 vertices, using maximum independent
  neighborhood sets for speed.

These checks are not used as proof, but they validate the construction against
the known failed route.
