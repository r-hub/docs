---
title: "R-hub services"
date: 2018-01-28T22:01:36+01:00
---

Other services built around the package builder include:

* R-hub Docker containers that allow [local debugging on Linux](#local-debugging)
* the possibility to deploy R-hub locally (not yet)
* Continuous integration (not there yet either)

R-hub also includes:

* A database (and API) of system requirements, accessible via an API, used by the package builder and usable by other external tools such as `containerit` and `codemetar`,
* A database (and API) of CRAN downloads from the RStudio CRAN mirror, useful to assess packages' popularity,
* A database (and API) of R versions,
* A database (and API) of CRAN packages, that's searchable,
* An unofficial mirror of all CRAN packages on GitHub, useful to search for code.