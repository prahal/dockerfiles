FROM debian:jessie
MAINTAINER Jessica Frazelle <jess@docker.com>

RUN apt-get update && apt-get install -y \
    ca-certificates \
    cowsay \
    curl \
    figlet \
    imagemagick \
    jp2a \
    python \
    --no-install-recommends

ENV HOME /root
WORKDIR $HOME

COPY ./lolcat /usr/bin/lolcat

RUN echo 'image_me() { convert $1 jpg:- | jp2a ${*:2} -; }' >> $HOME/.bashrc

ENTRYPOINT [ "bash" ]
