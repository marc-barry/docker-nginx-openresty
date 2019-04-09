DOCKER_ORG := middlenamesfirst
NAME := docker-nginx-openresty
GIT_COMMIT := $(shell git rev-parse --short=10 HEAD 2>/dev/null)

BASE_IMAGE_URL := $(DOCKER_ORG)/$(NAME)
IMAGE_URL := $(BASE_IMAGE_URL):$(GIT_COMMIT)

docker-build:
	docker build --pull -t ${IMAGE_URL} .

docker-push:
	docker push "${IMAGE_URL}"
