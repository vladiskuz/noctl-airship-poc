.PHONY: fix vet fmt test lint

GOPATH := $(shell go env GOPATH)

all: fix vet fmt test lint

fix:
	go fix ./...

fmt:
	go fmt ./...

lint:
	(which $(GOPATH)/bin/golangci-lint || go get github.com/golangci/golangci-lint/cmd/golangci-lint)
	$(GOPATH)/bin/golangci-lint run ./...

test:
	go test -cover ./...

vet:
	go vet ./...

image:
	docker build -f Dockerfile ./ -t quay.io/aodinokov/grep:v0.0.1
	#docker push quay.io/aodinokov/grep:v0.0.1
