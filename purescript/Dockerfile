# Base image choice is arbitrary.
# Maybe Ubuntu would be better?
FROM debian:jessie-slim

MAINTAINER Jordan Mackie <jmackie@protonmail.com>

# Version arguments
ARG PURS_VERSION=0.12.0
ARG PSC_PACKAGE_VERSION=0.4.2

# The usual update+install preamble
RUN apt-get update && \
    apt-get install -y --no-install-recommends \
        ca-certificates \
        curl \
        git && \
    rm -rf /var/lib/apt/lists/*

# Download the purescript compiler (purs)
RUN cd /tmp && \
    curl -L -o purescript.tar.gz https://github.com/purescript/purescript/releases/download/v${PURS_VERSION}/linux64.tar.gz && \
    tar xvzf purescript.tar.gz && \
    mv ./purescript/purs /bin/purs

# Download the purescript package manager (psc-package)
RUN cd /tmp && \
    curl -L -o psc-package.tar.gz https://github.com/purescript/psc-package/releases/download/v${PSC_PACKAGE_VERSION}/linux64.tar.gz && \
    tar xvzf psc-package.tar.gz && \
    mv ./psc-package/psc-package /bin/psc-package
