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
commit.summary=Some description of the release
project.name=Foo (Optional only needed if you don't set a repo environment variable
```

Currently you need 3 environment variables available

```
username=YOUR_USER_NAME
password=YOUR_PASSWORD
owner=THE_OWNER_OF_REPO
repo=(Optional defaults to project.name in properties)
```


Then just setup your build pipeline to trigger this project
