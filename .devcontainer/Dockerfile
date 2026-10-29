FROM mcr.microsoft.com/devcontainers/base:ubuntu-24.04

ENV DEBIAN_FRONTEND=noninteractive

USER root

RUN apt-get update && apt-get install -y --no-install-recommends \
    bc bison build-essential ca-certificates ccache clang \
    cmake curl flex g++ gcc git git-lfs gnupg gperf \
    libelf-dev libncurses-dev libssl-dev lld llvm lz4 \
    make openssh-server openssl pahole perl python3 \
    python3-pip python3-venv rsync unzip wget xz-utils \
    zip zstd device-tree-compiler dwarves sudo \
    && rm -rf /var/lib/apt/lists/*

RUN mkdir -p /run/sshd /root/.ssh \
    && chmod 700 /root/.ssh \
    && printf '%s\n' \
       'Port 2222' \
       'PermitRootLogin prohibit-password' \
       'PubkeyAuthentication yes' \
       'PasswordAuthentication no' \
       'KbdInteractiveAuthentication no' \
       'PermitEmptyPasswords no' \
       > /etc/ssh/sshd_config.d/codespace.conf

EXPOSE 2222

CMD ["/bin/bash", "-lc", "mkdir -p /run/sshd && /usr/sbin/sshd && exec sleep infinity"]
