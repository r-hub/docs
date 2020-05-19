---
title: "System requirements"
date: 2018-01-28T21:55:52+01:00
anchor: "sysreqs"
level: 2
weight: 19
---

To make sure system requirements are met for your package,

* Put the information in the `SystemRequirements` field of `DESCRIPTION`.
* Make sure the system requirements are matched by [`sysreqsdb`](https://github.com/r-hub/sysreqsdb/#sysreqs). If not, [contribute to `sysreqsdb`](https://github.com/r-hub/sysreqsdb/#contributing). Example: [`magick`'s DESCRIPTION](https://github.com/ropensci/magick/blob/a50201fd713eed1fdbc303821e45f9fdf5f7f63e/DESCRIPTION#L19), [corresponding `sysreqsdb` entry](https://raw.githubusercontent.com/r-hub/sysreqsdb/master/sysreqs/magick%2B%2B.json).

*We hope to soon use `sysreqsdb` for all platforms. At the moment, R-hub only uses `sysreqsdb` to install system requirements _on Linux platforms_.* For macOS and Windows, at the moment, to ensure system requirements are installed, you might open an [issue asking for its installation on the platform directly](https://github.com/r-hub/rhub/issues/) especially for commonly used third-party software (see e.g. [this CRAN list](https://cran.r-project.org/bin/windows/contrib/ThirdPartySoftware.html)), and in general, if you have trouble getting the system requirements met on any R-hub platform, [get in touch](#about-r-hub-in-particular).