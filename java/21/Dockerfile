FROM        --platform=$TARGETOS/$TARGETARCH ghcr.io/pterodactyl/yolks:java_21

# temporarily elevate perms
USER root

# install jemalloc
RUN apt install -y libjemalloc2

# tell java to use jemalloc
ENV LD_PRELOAD=/usr/lib/x86_64-linux-gnu/libjemalloc.so.2

# go back to container user
USER container