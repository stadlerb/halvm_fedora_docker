#
# Fedora HaLVM Installation in a Docker Container
# ==================================================
#
# Create a basic docker container with an HaLVM installation in /opt/halvm.
#
# NOTE: Docker must be installed and the current user must be privileged to
#       use docker.
#
SHELL=/bin/bash

REPO=stadlerb
CONTAINER=halvm-fedora-runtime
IMAGE=$(REPO)/halvm-fedora-runtime

# Create a docker container from a docker image with HaLVM installed:
.PHONY: container
container: clean-container image
	docker create -i -t --name $(CONTAINER) $(IMAGE):latest

# Start a shell inside the finished container:
.PHONY: run
run:
	docker start -a -i $(CONTAINER)

# Install all build dependencies and build HaLVM into a docker container:
.PHONY: image
image: Dockerfile
	set -o pipefail && docker build -t $(IMAGE) . 2>&1 | tee build.log

# Remove the docker container, but not the image:
.PHONY: clean-container
clean-container:
	-docker rm $(CONTAINER)

# Remove the docker container AND image:
.PHONY: clean-image
clean-image: clean-container
	-rm build.log
	-docker rmi $(IMAGE):latest
