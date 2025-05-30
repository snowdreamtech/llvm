FROM snowdreamtech/debian:12.10.0

# OCI annotations to image
LABEL org.opencontainers.image.authors="Snowdream Tech" \
    org.opencontainers.image.title="LLVM Image Based On Debian" \
    org.opencontainers.image.description="Docker Images for LLVM on Debian. (i386,amd64,arm32v5,arm32v7,arm64,mips64le,ppc64le,s390x)" \
    org.opencontainers.image.documentation="https://hub.docker.com/r/snowdreamtech/llvm" \
    org.opencontainers.image.base.name="snowdreamtech/llvm:debian" \
    org.opencontainers.image.licenses="MIT" \
    org.opencontainers.image.source="https://github.com/snowdreamtech/llvm" \
    org.opencontainers.image.vendor="Snowdream Tech" \
    org.opencontainers.image.version="12.10.0" \
    org.opencontainers.image.url="https://github.com/snowdreamtech/llvm"

# Define an argument for the platform 
ARG TARGETPLATFORM

# keep the docker container running
ENV KEEPALIVE=1 \
    LLVM_VERSION=16

ARG GID=1000 \
    UID=1000  \
    USER=llvm \
    WORKDIR=/home/llvm

# Create a user with UID and GID
RUN set -eux \
    &&if [ "${USER}" != "root" ]; then \
    addgroup --gid ${GID} ${USER}; \
    adduser --home /home/${USER} --uid ${UID} --gid ${GID} --gecos ${USER} --shell /bin/bash --disabled-password ${USER}; \
    # sed -i "/%sudo/c ${USER} ALL=(ALL:ALL) NOPASSWD:ALL" /etc/sudoers; \
    fi \
    && apt-get -qqy --purge autoremove \
    && apt-get -qqy clean \
    && rm -rf /var/lib/apt/lists/* \
    && rm -rf /tmp/* \
    && rm -rf /var/tmp/* 

RUN set -eux \  
    && echo ${TARGETPLATFORM} \
    && apt-get -y update

# LLVM
RUN apt-get -y install libllvm${LLVM_VERSION} llvm-${LLVM_VERSION} llvm-${LLVM_VERSION}-dev llvm-${LLVM_VERSION}-doc llvm-${LLVM_VERSION}-examples llvm-${LLVM_VERSION}-runtime
#  Clang and co
RUN apt-get -y install clang-${LLVM_VERSION} clang-tools-${LLVM_VERSION} clang-${LLVM_VERSION}-doc libclang-common-${LLVM_VERSION}-dev libclang-${LLVM_VERSION}-dev libclang1-${LLVM_VERSION} clang-format-${LLVM_VERSION} python3-clang-${LLVM_VERSION} clangd-${LLVM_VERSION} clang-tidy-${LLVM_VERSION}
#  compiler-rt
RUN apt-get -y install libclang-rt-${LLVM_VERSION}-dev
#  polly
RUN apt-get -y install libpolly-${LLVM_VERSION}-dev
#  libfuzzer
RUN apt-get -y install libfuzzer-${LLVM_VERSION}-dev
#  lldb
RUN if [ "$TARGETPLATFORM" != "linux/mips64le" ]; then \
        apt-get -y install lldb-${LLVM_VERSION}; \
    fi
#  lld (linker)
RUN apt-get -y install lld-${LLVM_VERSION}
#  libc++
RUN apt-get -y install libc++-${LLVM_VERSION}-dev libc++abi-${LLVM_VERSION}-dev
#  OpenMP
RUN if [ "$TARGETPLATFORM" != "linux/arm/v5" ] && [ "$TARGETPLATFORM" != "linux/s390x" ]; then \
        apt-get -y install libomp-${LLVM_VERSION}-dev; \
    fi
#  libclc
RUN apt-get -y install libclc-${LLVM_VERSION}-dev
#  libunwind
RUN if [ "$TARGETPLATFORM" != "linux/arm/v5" ] && [ "$TARGETPLATFORM" != "linux/mips64le" ] && [ "$TARGETPLATFORM" != "linux/s390x" ]; then \
        apt-get -y install libunwind-${LLVM_VERSION}-dev; \
    fi
#  mlir
RUN apt-get -y install libmlir-${LLVM_VERSION}-dev mlir-${LLVM_VERSION}-tools
#  bolt
RUN if [ "$TARGETPLATFORM" == "linux/amd64" ]; then \
        apt-get -y install libbolt-${LLVM_VERSION}-dev bolt-${LLVM_VERSION}; \
    fi
#  flang
RUN if [ "$TARGETPLATFORM" == "linux/amd64" ] || [ "$TARGETPLATFORM" == "linux/arm64" ] || [ "$TARGETPLATFORM" == "linux/mips64el" ] || [ "$TARGETPLATFORM" == "linux/ppc64el" ]; then \
        apt-get -y install flang-${LLVM_VERSION}; \
    fi
#  wasm support
RUN apt-get -y install libclang-rt-${LLVM_VERSION}-dev-wasm32 libclang-rt-${LLVM_VERSION}-dev-wasm64 libc++-${LLVM_VERSION}-dev-wasm32 libc++abi-${LLVM_VERSION}-dev-wasm32 libclang-rt-${LLVM_VERSION}-dev-wasm32 libclang-rt-${LLVM_VERSION}-dev-wasm64

RUN apt-get -y --purge autoremove \
    && apt-get -y clean \
    && rm -rf /var/lib/apt/lists/* \
    && rm -rf /tmp/* \
    && rm -rf /var/tmp/*

# Switch to the user
USER ${USER}

# Set the workdir
WORKDIR ${WORKDIR}

COPY update-alternatives-llvm.sh docker-entrypoint.sh /usr/local/bin/

ENTRYPOINT ["docker-entrypoint.sh"]