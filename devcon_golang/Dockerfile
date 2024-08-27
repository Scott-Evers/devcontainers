ARG DEPENDENCY_VER=latest
FROM scottaevers/base:${DEPENDENCY_VER}


# RUN apk update

# ## Common utilities for building rust apps
# RUN apk add build-base

# Install Rust via rustup
RUN  rm -rf /usr/local/go && curl -L https://go.dev/dl/go1.23.0.linux-amd64.tar.gz | tar -zx -C /usr/local
RUN fish_add_path -U /usr/local/go/bin
