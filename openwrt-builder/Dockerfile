FROM docker.io/debian:bookworm-slim

ARG BUILDBOT_UID
ARG BUILDBOT_GID

ENV GCC_COLORS='error=01;31:warning=01;35:note=01;36:caret=01;32:locus=01:quote=01'
WORKDIR /workdir

RUN apt update && apt install --no-install-recommends --no-install-suggests --yes \
    'build-essential' \
    'ca-certificates' \
    'clang' \
    'flex' \
    'bison' \
    'g++' \
    'gawk' \
    'gcc-multilib' \
    'g++-multilib' \
    'gettext' \
    'git' \
    'libncurses5-dev' \
    'libssl-dev' \
    'python3-distutils' \
    'python3-setuptools' \
    'rsync' \
    'swig' \
    'unzip' \
    'zlib1g-dev' \
    'file' \
    'wget' \
  && \
  apt clean && \
  rm -f -r '/var/lib/apt/lists/*' && \
  groupadd -g $BUILDBOT_GID buildbot && \
  useradd -m -u $BUILDBOT_UID -g $BUILDBOT_GID -s '/bin/bash' 'buildbot'

USER buildbot

