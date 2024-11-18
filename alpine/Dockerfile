FROM snowdreamtech/alpine:3.20.3

# OCI annotations to image
LABEL org.opencontainers.image.authors="Snowdream Tech" \
    org.opencontainers.image.title="LLVM Image Based On Alpine" \
    org.opencontainers.image.description="Docker Images for LLVM on Alpine. (i386, amd64, arm32v6, arm32v7, arm64, ppc64le,riscv64, s390x)" \
    org.opencontainers.image.documentation="https://hub.docker.com/r/snowdreamtech/llvm" \
    org.opencontainers.image.base.name="snowdreamtech/llvm:alpine" \
    org.opencontainers.image.licenses="MIT" \
    org.opencontainers.image.source="https://github.com/snowdreamtech/llvm" \
    org.opencontainers.image.vendor="Snowdream Tech" \
    org.opencontainers.image.version="3.20.3" \
    org.opencontainers.image.url="https://github.com/snowdreamtech/llvm"

# keep the docker container running
ENV KEEPALIVE=1

RUN apk add --no-cache \
    clang18 \
    clang18-dev \
    llvm18 \
    llvm18-dev \
    lld \
    musl-dev \
    compiler-rt \
    cmake \
    ninja \
    python3

COPY docker-entrypoint.sh /usr/local/bin/

ENTRYPOINT ["docker-entrypoint.sh"]