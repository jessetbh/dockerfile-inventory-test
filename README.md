# dockerfile-inventory-test

A polyglot "shop" monorepo used to exercise Datadog's Dockerfile inventory scanning and
image source label pull requests. Nothing here is meant to be built or deployed.

Most Dockerfiles have no image source labels. A few are deliberately labeled, partially
labeled, or written in unusual forms; see `EXPECTED.md`.
