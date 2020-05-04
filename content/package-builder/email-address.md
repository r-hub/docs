---
title: "What if you are not the package maintainer?"
date: 2018-01-28T21:55:52+01:00
anchor: "email-address"
level: 2
weight: 14
---

By default, R-hub builder (webform, package) will use the email address of the package maintainer listed in `DESCRIPTION` to identify you and send you an email after the build. You can however override this, via the [advanced tab of the webform](https://builder.r-hub.io/advanced), and the `email` argument of the [`rhub::check()` functions](https://r-hub.github.io/rhub/reference/).