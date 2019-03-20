---
title: "Reproduce a bug uncovered by R-hub?"
date: 2018-01-28T21:55:52+01:00
anchor: "local-debugging"
weight: 24

---

You could in theory experiment with your package, tinker with the code, submit it to R-hub again until the bug disappears but this would have a high turnaroud so is not optimal for debugging.

You can debug locally for Linux platforms, with R-hub Docker containers, no matter your operating system, granted you were able to install Docker itself.

https://github.com/r-hub/rhub-linux-builders#rhub-linux-builders

For other platforms that you do not have access to locally, you might need to [ask for help](#pkg-dev-help). And if you think the problem is due to R-hub rather than due to your package, [get in touch](#about-r-hub-in-particular).