# Directory API Test Fixture

[简体中文](README.zh-CN.md)

A local Gin service for testing employee-directory imports. Its sample responses map employees to departments and use parent IDs to represent a department tree.

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
