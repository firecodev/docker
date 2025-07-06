# OpenWrt Builder

## Install required packages

```sh
sudo apt update && sudo apt install -y make
```

## Create the build container image

```sh
make image
```

## Enter the OpenWrt source directory

This directory can be empty for now and clone the source in the container later.

```sh
cd <openwrt-src>
```

## Launch build container from the image

```sh
make -f <dir-of-Makefile>/Makefile run
```
