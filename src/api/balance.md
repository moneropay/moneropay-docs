## GET /balance 
Get the entire wallet balance.
### Request
```sh
curl -s -X GET "${endpoint}/balance"
```
### Response
```json
{
  "total": 2513444800,
  "unlocked": 800000000,
}
```
> For querying received amounts to subaddresses take a look at [`GET /receive/:address`](/api/receive.html#get-receiveaddress) endpoint.
