## GET /health
Check if required services are up.
### Request
```sh
curl -s -X GET "${endpoint}/health"
```
### Response
#### 200 OK
```json
{
  "status": 200,
  "services": {
    "walletrpc": true,
    "postgresql": true
  }
}
```
#### 503 Service Unavailable
```json
{
  "status": 503,
  "services": {
    "walletrpc": false,
    "postgresql": true
  }
}
```
