---
title: "Email validation, why and how?"
date: 2018-01-28T21:55:52+01:00
anchor: "email-validation"
level: 2
weight: 14
---

To use the R-hub package builder, your email address needs to be validated. This allows R-hub to send you results after builds, and might be used for adding use quotas later on.

Email validation with the `rhub` package happens once and for all on each machine. Refer to [the package docs](https://r-hub.github.io/rhub/reference/validate_email.html).

Via the web interface, the validation happens 

* either via email, you'll need to copy-paste one token per package upload;

* or faster, using GitHub authentication if you have a GitHub account and your email address is listed publicly on your GitHub profile.