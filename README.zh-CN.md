# 目录接口测试服务

[English](README.md)

用 Gin 编写的本地通讯录测试服务。它返回员工与部门的关联数据，以及用于还原部门树的父部门 ID，便于联调导入流程。

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
