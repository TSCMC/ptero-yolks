FROM        --platform=$TARGETOS/$TARGETARCH ghcr.io/pterodactyl/yolks:java_21

# temporarily elevate perms
USER root

# install jemalloc
RUN apt install -y libjemalloc2

# tell java to use jemalloc
ENV LD_PRELOAD=""
RUN if [ "$TARGETARCH" = "amd64" ]; then \
        export LD_PRELOAD="/usr/lib/x86_64-linux-gnu/libjemalloc.so.2"; \
    elif [ "$TARGETARCH" = "arm64" ]; then \
        export LD_PRELOAD="/usr/lib/aarch64-linux-gnu/libjemalloc.so.2"; \
    fi && \
    echo "Using jemalloc from: $LD_PRELOAD" && \
    echo "LD_PRELOAD=$LD_PRELOAD" >> /etc/environment

ENV LD_PRELOAD=${LD_PRELOAD}

# go back to container user
USER container