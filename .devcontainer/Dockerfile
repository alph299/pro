FROM ubuntu:24.04

ENV DEBIAN_FRONTEND=noninteractive
ENV HOME=/root
ENV USER=root
ENV ARCH=x86_64

RUN apt-get update && apt-get install -y \
    build-essential bc bison flex \
    libssl-dev libelf-dev libncurses-dev \
    dwarves pahole cpio rsync kmod \
    git curl wget vim nano less file tree \
    python3 python3-pip python3-venv python3-dev \
    perl tar xz-utils zstd lz4 gzip unzip zip \
    patch diffutils pkg-config cmake ninja-build \
    clang llvm lld \
    gcc-aarch64-linux-gnu g++-aarch64-linux-gnu \
    gcc-arm-linux-gnueabihf g++-arm-linux-gnueabihf \
    gcc-riscv64-linux-gnu g++-riscv64-linux-gnu \
    qemu-system-x86 qemu-system-arm qemu-system-misc \
    ccache \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /workspace
CMD ["/bin/bash"]
