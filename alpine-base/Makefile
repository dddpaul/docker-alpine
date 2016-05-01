.PHONY: all build release

all:	build

build:
	@docker build --tag=dddpaul/alpine-base .

release: build
	@docker build --tag=dddpaul/alpine-base:$(shell cat VERSION) .
