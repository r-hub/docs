---
title: "How are dependencies installed?"
date: 2018-01-28T21:55:52+01:00
anchor: "pkg-deps"
level: 2
weight: 18

---

The R-hub package builder installs all package dependencies on-demand, at build/check time, from CRAN,
and possibly other sources, using the [`remotes` package](https://remotes.r-lib.org/). 

On platforms that make use of binaries, typically Windows and macOS, if your package depends on a package that is on CRAN that was only very recently released and that does not have a binary build yet, R-hub will try to build it. If it requires compilation,
then R-hub might not be able to build it. Should this happen, [please get in touch](#pkg-dev-help).

R-hub supports packages from other sources than CRAN (e.g. a package in development in a GitHub repository), this is useful for
testing your package with non-CRAN dependencies. Refer to [this `remotes` vignette](https://remotes.r-lib.org/articles/dependencies.html) for
details.
