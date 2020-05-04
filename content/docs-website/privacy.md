---
title: "R-hub docs' privacy policy"
date: 2018-01-28T21:55:52+01:00
anchor: "privacy"
level: 2
weight: 2
---

We use [Google Analytics](https://analytics.google.com/analytics/web/) to log data and ultimately improve the docs. Below are the [Hugo privacy settings](https://gohugo.io/about/hugo-and-gdpr/#googleanalytics) we use for Google Analytics, within [the Hugo config file for this website](https://github.com/r-hub/docs/blob/master/config.toml).

```yaml
  [privacy.googleAnalytics]
    anonymizeIP = true
    disable = false
    respectDoNotTrack = true
    useSessionStorage = true
```

This means

* IP addresses are anonymized within Google Analytics,

* The GA templates respect the “Do Not Track” HTTP header,

* The use of Cookies is disabled, instead Session Storage to Store the GA Client ID is used.

This website is deployed via [Netlify](https://www.netlify.com/gdpr/).

For more information, contact <admin@rhub.io>.
