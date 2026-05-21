# Local Verification Record

Date: 2026-05-21

The reproduction commands were executed in this directory:

```bash
lake exe cache get
lake build FormalConjectures.WrittenOnTheWallII.GraphConjecture141
```

Result:

```text
Build completed successfully (8002 jobs).
```

The target theorem file was then scanned for common placeholders:

```bash
rg -n "\\bsorry\\b|\\badmit\\b|axiom|constant|opaque" \
  FormalConjectures/WrittenOnTheWallII/GraphConjecture141.lean
```

Result: no matches.

The local `.lake/` directory was created by the verification run. It is a build
cache and dependency checkout, not handwritten proof source. A fresh user can
delete `.lake/` and recreate it with `lake exe cache get`.
