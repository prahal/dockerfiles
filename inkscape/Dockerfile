# Run inkscape in a container
#
# docker run -v /tmp/.X11-unix:/tmp/.X11-unix \
#     -v /inkscape/:/workspace \
#     -e DISPLAY=unix$DISPLAY \
#     infoslack/inkscape
#
FROM ubuntu:14.04
MAINTAINER Daniel Romero <infoslack@gmail.com>

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update && apt-get install -y \
    python-software-properties \
    software-properties-common

RUN add-apt-repository ppa:inkscape.dev/stable && \
    apt-get update && \
    apt-get install -y -qq --no-install-recommends inkscape && \
    rm -rf /var/lib/apt/lists/*

VOLUME /workspace
WORKDIR /workspace

ENTRYPOINT [ "inkscape" ]
