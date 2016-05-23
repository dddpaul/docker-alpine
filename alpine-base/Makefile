.PHONY: all build release deploy

all:	build

build:
	@docker build --tag=dddpaul/alpine-base .

release: build
	@docker build --tag=dddpaul/alpine-base:$(shell cat VERSION) .

deploy:  release
	@docker push dddpaul/alpine-base:$(shell cat VERSION)
