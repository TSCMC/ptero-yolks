FROM        --platform=$TARGETOS/$TARGETARCH ghcr.io/pterodactyl/yolks:java_21

# install jemalloc
RUN apt install -y jemalloc

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