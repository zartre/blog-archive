---
title: "Approaches to Using Single Dockerfile for Multi-arch Builds"
date: 2025-05-27
categories:
  - "Tutorial"
tags:
  - "dev"
public: true
---

Recently I had to migrate some services from amd64 instances to arm64
instances, specifically AWS Graviton. These services needed to install
their dependencies differently when building for amd64 and arm64.

My goal was to use a single Dockerfile to build both amd64 and arm64
images, with minimal to no changes in the build steps; it should be as
automatic as possible.

# Solution 1: Run commands dynamically

The most obvious solution would be to run commands based on the
architecture of the build machine.

```dockerfile
FROM alpine:3.21 AS base

RUN ARCH=$(uname -m) \
  && if [ "$ARCH" = "x86_64" ]; then \
  echo "Do something for amd64"; \
  elif [ "$ARCH" = "aarch64" ]; then \
  echo "Do something else for arm64"; \
  fi
```

Or you can use the `TARGETARCH` argument if you are using BuildKit.
This argument will be injected automatically during the build and
will be carried to subsequent stages.

```dockerfile
FROM alpine:3.21 AS base
ARG TARGETARCH

RUN if [ "$TARGETARCH" = "amd64" ]; then \
  echo "Do something for amd64"; \
  elif [ "$TARGETARCH" = "arm64" ]; then \
  echo "Do something else for arm64"; \
  fi
```

# Solution 2: Use a middleman image

Some operations need to happen in the Dockerfile itself rather than in
the build container. Take setting environment variables as an example.
You cannot do RUN export `SOME_VAR="some value"` and expect it to be
carried to the next build stage; it is not.

For this, we can create a 'middleman' image for adding something on
top of the next stage and utilise BuildKit's `TARGETARCH` to select the
middleman image as the base image dynamically based on the architecture.

The following example sets the path for `LD_PRELOAD` differently for
each architecture. Notice how the base image is chosen dynamically
through `FROM base-${TARGETARCH}`.

```dockerfile
FROM alpine:3.21 AS base
ARG TARGETARCH

# Do something

FROM base AS base-amd64
ENV LD_PRELOAD=/usr/lib/x86_64-linux-gnu/libjemalloc.so.2

FROM base AS base-arm64
ENV LD_PRELOAD=/usr/lib/aarch64-linux-gnu/libjemalloc.so.2

FROM base-${TARGETARCH} AS release

# Do something
```

Please feel free to share your solutions!
