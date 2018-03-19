build:
	protoc --proto_path=$(GOPATH)/src/github.com/leesavage/examples/service/srv/greeter-service --micro_out=. --go_out=. proto/greeter.proto
	GOOS=linux GOARCH=amd64 go build
	docker build -t greeter-service .

run:
	docker run -p 50051:50051 -e MICRO_SERVER_ADDRESS=:50051 -e MICRO_REGISTRY=mdns greeter-service