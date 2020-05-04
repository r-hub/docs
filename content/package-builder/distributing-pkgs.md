---
title: "How to build R packages for distributing them?"
date: 2018-01-28T21:55:52+01:00
anchor: "distributing-pkgs"
level: 2
weight: 17

---

Imagine you want to share your package with colleague working on a different operating system, without access to tools for building packages on that platform. How do you create an appropriate binary for your package?

### Once in a while

If you're only doing this sporadically, you can use R-hub builder to build your package on the platform corresponding to your colleague's computer. In the email you'll receive after a (hopefully successful) build, there's a link to _artifacts_ i.e. the built package that you can download and send to your colleague; and in `rhub`, the output check functions has [an `urls()` method returning the build and artifacts URLs ](https://r-hub.github.io/rhub/reference/rhub_check.html#details). 
Be careful, artifacts only remain online for a few days so download them as soon as you can.

### Regularly

If you want to regularly build and deploy your package on different platforms, what you are looking for is _continuous integration_.

* R-hub CI. Not at the moment.

* Appveyor (Windows). Each build has a [tab with artefacts](https://ci.appveyor.com/project/jeroen/gifski/build/job/g3ryly3s833lomlk/artifacts), and you could automate the workflow with scripts. Refer to [Appveyor docs](https://www.appveyor.com/docs/).

* Travis (MacOS, Linux, soon Windows). Refer to [Travis docs](https://docs.travis-ci.com/), for instance [the page about uploading artefacts](https://docs.travis-ci.com/user/uploading-artifacts/).

* Other CI services surely support similar options. 

Looking for help with one of these non R-hub CI services? Read [our section about getting help](#pkg-dev-help).