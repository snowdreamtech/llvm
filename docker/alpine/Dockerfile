# LLVM Image (Alpine Variant)
# Extends snowdreamtech/alpine with additional tooling and configuration.

FROM snowdreamtech/alpine:3.24.0

# Build-time Configuration
ARG BUILDTIME \
    VERSION \
    REVISION \
    KEEPALIVE=0 \
    CAP_NET_BIND_SERVICE=0 \
    LANG=C.UTF-8 \
    UMASK=022 \
    DEBUG=false \
    PASSWORDLESS_SUDO=false \
    PGID=0 \
    PUID=0 \
    USER=root \
    WORKDIR=/root \
    LLVM_VERSION=22.1.3-r0

# Standard OCI Metadata (https://github.com/opencontainers/image-spec)
LABEL org.opencontainers.image.authors="Snowdream Tech" \
    org.opencontainers.image.title="LLVM Image Based On Alpine" \
    org.opencontainers.image.description="Docker Images for LLVM on Alpine. (i386, amd64, arm32v6, arm32v7, arm64, ppc64le, riscv64, s390x)" \
    org.opencontainers.image.documentation="https://hub.docker.com/r/snowdreamtech/llvm" \
    org.opencontainers.image.base.name="snowdreamtech/alpine:3.24.0" \
    org.opencontainers.image.licenses="MIT" \
    org.opencontainers.image.source="https://github.com/snowdreamtech/llvm" \
    org.opencontainers.image.vendor="Snowdream Tech" \
    org.opencontainers.image.created="${BUILDTIME}" \
    org.opencontainers.image.revision="${REVISION}" \
    org.opencontainers.image.url="https://github.com/snowdreamtech/llvm"

# x-release-please-start-version
LABEL org.opencontainers.image.version="${VERSION:-19.1.0}"
# x-release-please-end

# Runtime Environment Configuration
ENV KEEPALIVE=${KEEPALIVE} \
    CAP_NET_BIND_SERVICE=${CAP_NET_BIND_SERVICE} \
    LANG=${LANG} \
    UMASK=${UMASK} \
    DEBUG=${DEBUG} \
    PASSWORDLESS_SUDO=${PASSWORDLESS_SUDO} \
    PGID=${PGID} \
    PUID=${PUID} \
    USER=${USER} \
    WORKDIR=${WORKDIR} \
    LLVM_VERSION=${LLVM_VERSION}

# Additional tooling and configuration for LLVM image
RUN apk update \
    && LLVM_BASE_VERSION=$(echo ${LLVM_VERSION} | cut -d- -f1) \
    && apk add --no-cache \
    "llvm=~${LLVM_BASE_VERSION}" \
    "clang=~${LLVM_BASE_VERSION}" \
    "clang-extra-tools=~${LLVM_BASE_VERSION}" \
    "clang-dev=~${LLVM_BASE_VERSION}" \
    "clang-static=~${LLVM_BASE_VERSION}" \
    lld \
    lldb \
    "compiler-rt=~${LLVM_BASE_VERSION}" \
    "libc++=~${LLVM_BASE_VERSION}" \
    "libc++-dev=~${LLVM_BASE_VERSION}" \
    "libc++-static=~${LLVM_BASE_VERSION}" \
    "llvm-dev=~${LLVM_BASE_VERSION}" \
    "llvm-static=~${LLVM_BASE_VERSION}" \
    lld-dev \
    lldb-dev \
    cmake \
    samurai \
    pkgconf \
    curl \
    wget \
    unzip \
    tar \
    xz \
    vim \
    meson \
    zip \
    bzip2 \
    gzip \
    zstd \
    gnupg \
    ca-certificates \
    file \
    tree \
    jq \
    openssl-dev \
    zlib-dev \
    autoconf \
    automake \
    libtool \
    m4 \
    patch \
    flex \
    bison \
    ccache \
    gettext \
    perl \
    python3 \
    rsync \
    bash \
    gawk \
    bc \
    dos2unix \
    ncurses-dev \
    readline-dev \
    libffi-dev \
    sqlite-dev \
    gdb \
    strace \
    valgrind \
    ltrace \
    linux-headers \
    elfutils-dev \
    coreutils \
    findutils \
    diffutils \
    sudo \
    fakeroot \
    texinfo \
    expat-dev \
    nasm \
    yasm \
    swig \
    gperf \
    bzip2-dev \
    xz-dev \
    zstd-dev

# Container Orchestration Files
COPY entrypoint.d /usr/local/bin/entrypoint.d

RUN chmod +x /usr/local/bin/entrypoint.d/*

# Standard Healthcheck (Verification of core system responsiveness)
HEALTHCHECK NONE

# Process Execution
USER root
WORKDIR /root
ENTRYPOINT ["docker-entrypoint.sh"]
CMD ["/bin/sh"]
