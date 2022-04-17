## GET /balance 
Get the entire wallets balance.
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
> For subaddress balance look at [`GET /receive/:address`](/api/receive.html#get-receiveaddress) endpoint.
