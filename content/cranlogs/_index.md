---
title: "Download counts of CRAN packages"
date: 2018-01-28T22:01:36+01:00
anchor: "cranlogs"
level: 1
weight: 550
---

R-hub simplifies your getting download counts of CRAN packages from [RStudio](http://www.rstudio.com)'s CRAN mirror download logs, that RStudio publishes daily at <http://cran-logs.rstudio.com>. The RStudio CRAN mirror is not the only CRAN mirror, but it’s a popular one: it’s the default choice for RStudio users. The actual number of downloads over all CRAN mirrors is unknown. Therefore, using numbers of downloads from that mirror is a _proxy_ for actual numbers of downloads, and when analysing it one has to assume the observed trends are representative of what happens via other mirrors.

* R-hub provides a web API of the data, [documented in its GitHub README](https://github.com/r-hub/cranlogs.app#the-api-of-the-cran-downloads-database). The service includes
    * [data](https://github.com/r-hub/cranlogs.app#web-api-docs): [downloads of R itself](https://github.com/r-hub/cranlogs.app#downloads-of-r), [downloads of packages over any time period](https://github.com/r-hub/cranlogs.app#total-downloads-over-a-period-downloadstotalperiodpackage1package2), [top downloads over the latest available day/week/month](https://github.com/r-hub/cranlogs.app#top-downloaded-packages-topperiodcount);
    * [badges](https://github.com/r-hub/cranlogs.app#badges).

* R-hub maintains an official R client for the API, the CRAN `cranlogs` package. [Refer to its documentation website](https://r-hub.github.io/cranlogs/).