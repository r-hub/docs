---
title: "CRAN source code mirror"
date: 2018-01-28T22:01:36+01:00
anchor: "cranatgh"
level: 1
weight: 500
---

R-hub unofficially mirrors CRAN packages to the [`cran` GitHub organization](https://github.com/cran/). Each CRAN package lives in its own GitHub repository, e.g. package Rcpp is at https://github.com/cran/Rcpp. All versions of all packages are included, and each version is a separate git commit, tagged with the version number. We tried to keep the original dates and authors/maintainers as well.

The main goal of CRAN @ GitHub is the **easy access to the source code or CRAN packages**. In particular, you can

* See differences between package versions, e.g. [what changed between 1.2.0 and 1.2.1](https://github.com/cran/crayon/commit/72b56a09cd4cbc787eb90a31d88f736d280af8b5) in crayon.

* Fork packages, and create patched versions of them, for your own purposes. 

* Use [GitHub search functionality](https://help.github.com/en/articles/about-searching-on-github).

R-hub mirror of CRAN packages is one of the sources used by [Jim Hester's `lookup` package](https://github.com/jimhester/lookup), that helps you lookup R full function definitions, including compiled code, S3 and S4 methods. 