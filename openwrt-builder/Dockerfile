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
  apt install --no-install-recommends --no-install-suggests --yes \
    'nano' \
    'quilt' \
  && \
  rm -f -r '/var/lib/apt/' && \
  rm -f -r '/var/cache/apt/' && \
  groupadd -g $BUILDBOT_GID buildbot && \
  useradd -m -u $BUILDBOT_UID -g $BUILDBOT_GID -s '/bin/bash' 'buildbot'

USER buildbot

# Setup quilt patch format
RUN cat <<EOF > ~/.quiltrc
QUILT_DIFF_ARGS="--no-timestamps --no-index -p ab --color=auto"
QUILT_REFRESH_ARGS="--no-timestamps --no-index -p ab"
QUILT_SERIES_ARGS="--color=auto"
QUILT_PATCH_OPTS="--unified"
QUILT_DIFF_OPTS="-p"
EDITOR="nano"
EOF

