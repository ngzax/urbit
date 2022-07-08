FROM debian:stable

USER root

RUN apt-get update && apt-get install -y curl vim xz-utils

RUN set -xe; \
  groupadd -f urbit && \
  useradd -g urbit -G sudo -m urbit -s /bin/bash

RUN mkdir -m 0755 /nix && chown urbit /nix

COPY bash_aliases  /home/urbit/.bash_aliases
COPY build-urbit   /home/urbit/build-urbit

RUN chmod a+x /home/urbit/build-urbit

USER urbit

RUN curl -L https://nixos.org/nix/install | sh
