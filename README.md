# Directory API Test Fixture

[简体中文](README.zh-CN.md)

A small Gin service that supplies sample employee and department data for testing directory integrations. Its responses include employee-to-department mappings and parent IDs for nested departments, so a client can develop and test its import logic against local data.

## Endpoints

| Endpoint | Response |
| --- | --- |
| `GET /hello` | Minimal JSON response for a smoke check. |
| `GET /members` | Sample members and departments. |
| `GET /members/pro` | Larger fixture behind a hard-coded demo token check. |
| `GET /members/plus` | Larger fixture with additional members and deeper department hierarchies. |

The handlers and fixture generators are in [main.go](main.go). The token check is a test fixture and should only be used locally.

## Run locally

The [Go module](go.mod) declares Go 1.19. Start the service from the repository root, then send a request from a second terminal.

```sh
go run .
```

```sh
curl -fsS http://localhost:3002/hello
curl -fsS http://localhost:3002/members
```
