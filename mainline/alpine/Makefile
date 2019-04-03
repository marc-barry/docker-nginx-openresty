DOCKER_ORG := middlenamesfirst
NAME := docker-nginx-openresty
GITCOMMIT := $(shell git rev-parse --short=10 HEAD 2>/dev/null)

BASE_IMAGE_URL := $(DOCKER_ORG)/$(NAME)
IMAGE_URL := $(BASE_IMAGE_URL):$(GITCOMMIT)

image-create:
	docker build --pull -t ${IMAGE_URL} .

image-push:
	docker login -u="${DOCKER_USERNAME}" -p="${DOCKER_PASSWORD}"
	docker tag "${IMAGE_URL}" "${BASE_IMAGE_URL}:latest"
	docker push "${IMAGE_URL}"
	docker push "${BASE_IMAGE_URL}:latest"