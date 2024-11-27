VERSION=0.2

# HELP
.PHONY: help

help: ## This help.
	@awk 'BEGIN {FS = ":.*?## "} /^[a-zA-Z_-]+:.*?## / {printf "\033[36m%-30s\033[0m %s\n", $$1, $$2}' $(MAKEFILE_LIST)

build: ## build docker image
	docker build -t stable-diffusion-webui-docker/automatic1111 .

push: ## tag and push docker image
	docker tag stable-diffusion-webui-docker/automatic1111:latest ghcr.io/jsnouffer/stable-diffusion-webui-docker/automatic1111:$(VERSION)
	docker push ghcr.io/jsnouffer/stable-diffusion-webui-docker/automatic1111:$(VERSION)
