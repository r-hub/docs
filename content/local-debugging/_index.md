---
title: "Local debugging with Docker"
date: 2018-01-28T22:01:36+01:00
anchor: "docker-images"
level: 1
weight: 200
---

[R-hub Linux images](https://github.com/r-hub/rhub-linux-builders#rhub-linux-builders) are available [on Docker hub](https://hub.docker.com/u/rhub), and [their source is open, on GitHub](https://github.com/r-hub/rhub-linux-builders). 

You can debug locally for Linux platforms, with R-hub Docker containers, no matter your operating system, granted you were able to install Docker itself. Find more information [in the README of R-hub Docker images repo](https://github.com/r-hub/rhub-linux-builders#rhub-linux-builders).

The `rhub` package provides some [helpers facilitating the use of R-hub Linux images](https://r-hub.github.io/rhub/articles/local-debugging.html).

There are other Docker images available online, not from R-hub, that might further help debugging R packages with C/C++ code: https://github.com/wch/r-debug; https://github.com/rocker-org/r-devel-san-clang; https://github.com/rocker-org/r-devel-san.

