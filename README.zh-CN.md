# 目录接口测试服务

[English](README.md)

一个用 Gin 编写的本地接口服务，为通讯录集成提供员工和部门样例。返回数据包含员工与部门的关联，以及用于还原部门树的父部门 ID，可以用来开发和调试导入逻辑。

## 接口

| 接口 | 返回内容 |
| --- | --- |
| `GET /hello` | 用于确认服务已启动的 JSON。 |
| `GET /members` | 员工和部门样例。 |
| `GET /members/pro` | 使用固定演示令牌校验，返回更大的样例数据。 |
| `GET /members/plus` | 返回更多员工和层级更深的部门数据。 |

路由和样例数据生成逻辑都在 [main.go](main.go)。令牌校验仅供本地测试。

## 本地运行

[Go 模块](go.mod)声明 Go 1.19。在仓库根目录启动服务，再用另一个终端发送请求。

```sh
go run .
```

```sh
curl -fsS http://localhost:3002/hello
curl -fsS http://localhost:3002/members
```
