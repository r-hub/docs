---
title: "What is R-hub?"
date: 2018-01-28T22:01:36+01:00
anchor: "intro"
weight: 1
---

R-hub is a collection of services to help R package development, free for all members of the community thanks to support from the [R Consortium](https://www.r-consortium.org/).

Its most prominent service is the [*package builder*](#package-builder) that allows building and checking any R package on several platforms and R versions, with submission happening via a webform or an R client.

### What R-hub is not

* A replacement of CRAN

### More details about R-hub services

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