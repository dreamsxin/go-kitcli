
# 命令

```shell
# 查看帮助
go run main.go help
go run main.go new -h
go run main.go generate -h
```

## hello 项目生成过程

```shell
# 生成一个服务，其目录名为 hello，创建一个 service 样板文件: hello/pkg/service/service.go
go run ..\main.go new service hello

# 修改 hello/pkg/service/service.go 增加接口

# 根据 service 接口生成代码
# 生成: hello/cmd/main.go、hello/cmd/service/service.go、hello/cmd/service/service_gen.go
# 生成: hello/pkg/service/middleware.go、hello/pkg/service/service.go
# 生成: hello/pkg/endpoint/endpoint.go、hello/pkg/endpoint/endpoint_gen.go
# 生成: hello/pkg/http/handler.go、hello/pkg/http/handler_gen.go
go run ..\main.go generate service hello

# 创建 endpoint 中间件: hello/pkg/endpoint/middleware.go
go run ..\main.go generate service hello -w
```

### 运行

```shell
go mod tidy
go run .\cmd\main.go
```