ARG DEPENDENCY_VER=latest
FROM scottaevers/base:${DEPENDENCY_VER}


RUN apk update

## Common utilities for building rust apps
RUN apk add build-base

# Install Rust via rustup
RUN curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- -y
