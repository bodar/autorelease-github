autorelease-github
==================

Automated release via GitHub API for your build pipeline

This is a very simple project than takes N number of files and uploads them via the [GitHub API](https://developer.github.com/v3/repos/releases/) using bash, curl and jq.

It's designed to be drop-in release build in your build pipeline. The input is a bunch of files and one property file dropped into the artifacts folder. 

For example:
```
artifacts/foo-42.jar
artifacts/bar-42.jar
artifacts/release.properties
```

And release.properties contains

```
release.files=foo-42.jar,bar-42.jar
```


Then just setup your build pipeline to trigger this project
