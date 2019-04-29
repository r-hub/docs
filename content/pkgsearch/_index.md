---
title: "Search CRAN packages"
date: 2018-01-28T22:01:36+01:00
anchor: "pkgsearch"
weight: 600
---

R-hub supports the search _of_ and _about_ CRAN packages. This is different from [R-hub's support of code search _in_ CRAN packages](#cranatgh).

The search _of_ CRAN packages, e.g. find all CRAN packages related to GLMs, is powered by [R-hub search web service](https://github.com/metacran/search). R-hub also maintains an official R client, the [CRAN `pkgsearch` package](https://r-hub.github.io/pkgsearch/index.html).

The search _about_ CRAN packages, e.g. get metadata of `httr` version 0.3, or get CRAN events (releases, archivals), is powered by [R-hub crandb service](https://github.com/metacran/crandb) that currently has its own R client, [`crandb`](https://github.com/metacran/crandb). The script in [crandb-updater GitHub repo](https://github.com/metacran/crandb-updater) is used to keep the database up-to-date with CRAN.