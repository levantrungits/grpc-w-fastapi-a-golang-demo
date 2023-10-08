## Connect FastAPI & Golang services using gRPC


python
#
go
#
grpc
#
microservices
#


### I. Golang services

#### 1. Initialize the go application with
```
$ go mod init auth-ms
```

#### 2. Generate the gRPC code
```
$ go install google.golang.org/protobuf/cmd/protoc-gen-go@v1.28
$ go install google.golang.org/grpc/cmd/protoc-gen-go-grpc@v1.2
$ protoc --go_out=. --go_grpc_out=. protobufs/auth.proto

 protoc --go_out=. --go_opt=paths=. \
    --go-grpc_out=. --go-grpc_opt=paths=. protobufs/auth.proto
```
more information:
```
https://grpc.io/docs/languages/go/quickstart/
```

#### 3. Update the dependencies
```
$ go mod tidy
```

#### 4. Start the gRPC server and keep it opened
```
$ go run main.go -port=8080
```


### II. FastAPI services
