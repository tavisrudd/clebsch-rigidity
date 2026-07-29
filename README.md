# Clebsch rigidity paper

This repository contains the rigidity and decoder manuscript
*Reconstructing the Clebsch code from its deep-hole syndrome locus*.

Its scope is rigidity, quantitative gaps, decoding, automorphisms, support
bipartition, Brianchon reconstruction, order-11 uniqueness, the
`4 <= k <= 8` classification, and their verification architecture. It does
not depend on the factorization or later Clebsch-passage results.

Build `clebsch_rigidity.tex` with:

```text
latexmk -xelatex -interaction=nonstopmode -halt-on-error clebsch_rigidity.tex
```

The Paper I verification surface is under `verification/`. It contains the
nineteen-row statement identity, trust manifest, validator, clean release
runner, unit tests, and deterministic successful output. The eleven selected
exact checkers and pinned Nix environment are release-local; the aggregate
formal gate is `RelativeConicArcs/Gates/ClebschRigidityTrust.lean` in the
order-11 certificate repository.

The human-scale formal source is distributed in
[`finitegeom`](https://github.com/tavisrudd/finitegeom), pinned at commit
`77c0d6bb5a45a1aa15a0ab90b7db307e1a1804d2`. The generated order-11 action,
orbit, and decoder modules are in
[`finitegeom-clebsch-q11-certificates`](https://github.com/tavisrudd/finitegeom-clebsch-q11-certificates),
pinned at commit `f6912c4c020b8bf9e3e7bd67c486af9275634989`.
The formal companion's version-independent archival locator is the Zenodo
concept DOI
[`10.5281/zenodo.21650878`](https://doi.org/10.5281/zenodo.21650878).
From this directory, supply a checkout of the certificate repository
as `--lean-root`:

```text
nix develop --command \
  python3 verification/verify_release.py \
  --lean-root /absolute/path/to/finitegeom-clebsch-q11-certificates
```
