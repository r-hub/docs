---
title: "What R-hub platform(s)?"
date: 2018-01-28T21:55:52+01:00
anchor: "which-platform"
level: 2
weight: 13
---

With R-hub you can build and check your package on 20 platforms (different operating systems/architectures, different R versions). It is very easy to [check all boxes in the webform](https://builder.r-hub.io/advanced) or to use `rhub::platforms()[,1]` as value for the `platform` argument of `rhub::check()`, but probably useless, a waste of R-hub resources and a waste of time for you (20 emails with very similar results!). Just because you can doesn't mean you should! Here are a few tips to help you choose not too many platforms.

### If you want to be confident your package works on all platforms, in particular for a CRAN submission

Use the R-hub platforms that are closest to platforms used by CRAN on submission:

* _Fedora Linux, R-devel, clang, gfortran_,
* _Ubuntu Linux 16.04 LTS, R-release, GCC_,
* _Windows Server 2008 R2 SP1, R-devel, 32/64 bit_,
* and, if your package needs compilation, _Debian Linux, R-devel, GCC ASAN/UBSAN_.

In general you'll be better off [using `rhub` rather than the web form](#pkg-vs-web). In particular, running `rhub::check_for_cran()` will automatically select the platforms mentioned above, including guessing whether your package needs compilation.

### If you want to reproduce a CRAN error on an exotic platform

Choose the platform that's [closest to the CRAN platform](#rhub-cran-platforms).
