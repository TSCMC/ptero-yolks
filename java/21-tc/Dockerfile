FROM        --platform=$TARGETOS/$TARGETARCH ghcr.io/pterodactyl/yolks:java_21

# temporarily elevate perms
USER root

# install tcmalloc
RUN apt install -y libtcmalloc-minimal4

# tell java to use tcmalloc
ENV LD_PRELOAD=/usr/lib/x86_64-linux-gnu/libtcmalloc_minimal.so.4

# go back to container user
USER container