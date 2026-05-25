# Natural-language proof for WOWII Conjecture 322

Let `G` be a finite connected simple graph with at least five vertices.  Assume that
every open neighborhood has independence number at most one.

1. The local hypothesis makes each open neighborhood a clique.  If two distinct
   vertices `x,y` are both adjacent to `v` and are not adjacent to each other, then
   `{x,y}` is an independent set of size two in `G[N(v)]`, contradicting the
   hypothesis.
2. The graph is complete.  Given distinct vertices `a,b`, choose a shortest path
   `a = p0, p1, ..., pk = b`.  If `k >= 2`, then `p0` and `p2` lie in `N(p1)`, so
   they are adjacent by the previous point.  This shortens the path, contradicting
   shortestness.  Hence `k = 1`, and every pair of distinct vertices is adjacent.
3. Complete graphs on at least two vertices are well totally dominated.  Every
   two-element set is a minimal total dominating set, no one-element set can be
   total dominating, and any total dominating set of size at least three is not
   minimal because deleting one selected vertex leaves at least two selected
   vertices.  Therefore all minimal total dominating sets have cardinality two.

Combining these three points proves `SimpleGraph.conjecture322`.
