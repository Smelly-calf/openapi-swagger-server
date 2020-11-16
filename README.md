# Go API Server for swagger

This is a sample server Petstore server. 生成代码地址：[https://editor.swagger.io/](https://editor.swagger.io/)

swagger.yaml 编写遵循 OpenAPI 规范：[https://github.com/OAI/OpenAPI-Specification](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.0.0.md#examples-object)

本项目基于 OpenAPI 3.0.0 规范生成。

如自定义 Response schema:

接口 responses 小节新增 "200" 接口规范
```
responses:
        "200":
          description: your car appointment has been booked
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/SuccessResponse'
              example:
                $ref: http://foo.bar#/examples/address-example.json
```

schemas 小节新增 SuccessResponse 定义 
```
schemas:
   SuccessResponse:
      type: object
      properties:
        code:
          type: string
          description: http status
        message:
          type: string
      example:
        code: 200
        message: ok
      xml:
        name: SuccessResponse
```
# 生成 go.mod

go mod init go-server-server-generated

# 启动

本地启动：go run main.go

# 访问

本地 http://localhost:8080/v2/ 请求服务

其他Method用 postman 请求

# client

也可以在 [https://editor.swagger.io/](https://editor.swagger.io/) 生成client代码
