ROOT_DIR        := $(dir $(realpath $(lastword $(MAKEFILE_LIST))))

CT_IMAGE_NAME   := openwrt-builder
CT_IMAGE_TAG    := ${USER}

test:
	@echo $(ROOT_DIR)

image: $(ROOT_DIR)/Dockerfile
	docker build --build-arg BUILDBOT_UID=$(shell id -u) --build-arg BUILDBOT_GID=$(shell id -g) --rm --tag $(CT_IMAGE_NAME):$(CT_IMAGE_TAG) --file $(ROOT_DIR)/Dockerfile $(ROOT_DIR)

run:
	docker run --interactive --rm --tty --ulimit 'nofile=1024:262144' --volume "$(shell pwd):/workdir" --workdir '/workdir' $(CT_IMAGE_NAME):$(CT_IMAGE_TAG) /bin/bash

