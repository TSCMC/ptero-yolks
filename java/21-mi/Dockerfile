FROM        --platform=$TARGETOS/$TARGETARCH ghcr.io/pterodactyl/yolks:java_21

# temporarily elevate perms
USER root

# install jemalloc
RUN apt install -y libmimalloc3

# tell java to use jemalloc
ENV LD_PRELOAD=/usr/lib/x86_64-linux-gnu/libmimalloc.so

# go back to container user
USER container