FROM ubuntu:24.04

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install -y \
    cmake \
    ninja-build \
    clang \
    clang-tools \
    clang-format \
    clang-tidy \
    lld \
    mingw-w64 \
    curl \
    git \
    python3.12 python3-pip \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /workspace

CMD ["/bin/bash"]